<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-card :loading="loading">
        <v-card-title class="headline">Claim Clairicature NFT</v-card-title>
        <v-card-text>
          <v-btn
            v-if="showWalletConnect"
            :loading="loading"
            x-large
            color="primary"
            class="mr-4"
            @click="connectWallet"
          >
            Connect Wallet
          </v-btn>
          <div v-else>
            <p class="subtitle-1">Web3 Address: {{ web3Address }}</p>
            <v-btn
              v-if="showSignMessage"
              :loading="loading"
              x-large
              color="primary"
              class="mr-4"
              @click="signSecret"
            >
              Sign Message
            </v-btn>
            <v-btn
              v-else-if="showClaimNFT"
              :loading="loading"
              x-large
              color="primary"
              class="mr-4"
              @click="claimNFT"
            >
              Claim NFT
            </v-btn>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import { ethers } from 'ethers'
import Web3Modal from 'web3modal'
import WalletConnectProvider from '@walletconnect/web3-provider'

const providerOptions = {
  walletconnect: {
    package: WalletConnectProvider, // required
    options: {
      rpc: {
        80001: 'https://rpc-mumbai.maticvigil.com',
        137: 'https://polygon-rpc.com',
      },
    },
  },
}

const web3Modal = new Web3Modal({
  cacheProvider: true,
  providerOptions,
})

export default {
  name: 'ClaimPage',
  data() {
    return {
      secret: this.$route.query.secret,
      signer: null,
      web3Address: null,
      loading: false,
      signature: null,
      employeeId: null,
      openSeaUrl: null,
    }
  },
  computed: {
    showWalletConnect() {
      return this.signer === null || this.web3Address === null
    },
    showSignMessage() {
      return (
        this.signer !== null &&
        this.web3Address !== null &&
        this.signature === null
      )
    },
    showClaimNFT() {
      return (
        this.signer !== null &&
        this.web3Address !== null &&
        this.signature !== null &&
        this.employeeId === null
      )
    },
  },
  mounted() {
    this.validateSecret()
  },
  methods: {
    validateSecret() {
      const uuidPattern =
        /^[0-9a-f]{8}-[0-9a-f]{4}-[0-5][0-9a-f]{3}-[089ab][0-9a-f]{3}-[0-9a-f]{12}$/i
      const isUuid = uuidPattern.test(this.secret)
      if (!isUuid) {
        this.$swal.fire({
          title:
            '<p style="font-family: Roboto, sans-serif">Missing Secret Claim Code</p>',
          icon: 'warning',
          backdrop: false,
          allowEscapeKey: false,
          allowEnterKey: false,
          showConfirmButton: false,
        })
      }
    },
    async connectWallet() {
      try {
        this.loading = true
        const instance = await web3Modal.connect()
        const provider = new ethers.providers.Web3Provider(instance)
        this.signer = provider.getSigner()
        this.web3Address = await this.signer.getAddress()
      } catch (error) {
        this.signer = null
        this.web3Address = null
      } finally {
        this.loading = false
      }
    },
    async signSecret() {
      this.loading = true
      this.signature = await this.signer.signMessage(this.secret)
      this.loading = false
    },
    async claimNFT() {
      try {
        this.loading = true
        const { data } = await this.$axios.post('/claim', {
          secret: this.secret,
          signature: this.signature,
          web3Address: this.web3Address,
        })
        this.employeeId = data.id
        this.openSeaUrl = data.openSeaUrl
        this.$swal.fire({
          title: `<p style="font-family: Roboto, sans-serif">Waiting For Mint Confirmation...</p>`,
          icon: 'info',
          backdrop: false,
          allowEscapeKey: false,
          allowEnterKey: false,
          showConfirmButton: false,
        })
        const confirmIntervalId = setInterval(async () => {
          const { data } = await this.$axios.get(
            `/is-confirmed/${this.employeeId}`
          )
          if (data.confirmed) {
            clearInterval(confirmIntervalId)
            this.loading = false
            this.$swal.close()
            this.$swal.fire({
              title: `<p style="font-family: Roboto, sans-serif">Clairicature NFT Claimed 🍻</p>`,
              html: `<a href="${this.openSeaUrl}" class="v-btn primary" style="font-family: Roboto, sans-serif">View On OpenSea</a>`,
              icon: 'success',
              backdrop: false,
              allowEscapeKey: false,
              allowEnterKey: false,
              showConfirmButton: false,
            })
          }
        }, 10000)
      } catch (error) {
        const message = error.response.data.message
          .split('_')
          .map(
            (word) => `${word[0].toUpperCase()}${word.slice(1).toLowerCase()}`
          )
          .join(' ')
        this.$swal.fire({
          title: `<p style="font-family: Roboto, sans-serif">${message}</p>`,
          icon: 'error',
        })
        this.loading = false
      }
    },
  },
}
</script>
