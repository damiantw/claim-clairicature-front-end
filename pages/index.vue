<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-card>
        <v-card-title class="headline">Claim Clairicature NFT</v-card-title>
        <v-form
          ref="form"
          v-model="valid"
          lazy-validation
          @submit.prevent="submit"
        >
          <v-card-text>
            <v-text-field
              v-model="email"
              :loading="loading"
              :rules="[rules.required, rules.email]"
              solo-inverted
              label="E-mail"
            ></v-text-field>
            <v-btn
              :loading="loading"
              :disabled="!valid"
              x-large
              color="primary"
              class="mr-4"
              @click="submit"
            >
              Verify Email
            </v-btn>
          </v-card-text>
        </v-form>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      email: '',
      valid: true,
      loading: false,
      rules: {
        required: (value) => !!value || 'Required.',
        email: (value) => {
          const pattern =
            /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
          return pattern.test(value) || 'Invalid e-mail.'
        },
      },
    }
  },
  methods: {
    async submit() {
      if (!this.$refs.form.validate()) {
        return
      }
      try {
        this.loading = true
        await this.$axios.post('/verify-email', {
          email: this.email,
        })
        this.$swal.fire({
          title: `<p style="font-family: Roboto, sans-serif">Verification Link Sent To: ${this.email}</p>`,
          icon: 'success',
        })
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
      } finally {
        this.loading = false
        this.$refs.form.reset()
      }
    },
  },
}
</script>
