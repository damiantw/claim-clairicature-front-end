<template>
  <v-row>
    <v-col cols="12">
      <v-card>
        <v-card-title class="title"> FAQs </v-card-title>
        <v-card-text>
          <v-expansion-panels accordion>
            <v-expansion-panel>
              <v-expansion-panel-header
                >How Do I Claim My Clairicature NFT?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>You'll need a Web3 wallet.</p>
                <p>
                  The
                  <a href="https://metamask.io/">MetaMask browser extension</a>
                  is recommended.
                </p>
                <p>
                  First, enter your @getclair.com email address and click the
                  'Verify Email' button.
                </p>
                <p>
                  Check your inbox for a message that contains a link with the
                  secret code to mint your unique Clairicature NFT.
                </p>
                <p>Click the link and connect your Web3 wallet.</p>
                <p>
                  You will then be prompted to sign a message that contains your
                  secret minting key using your Web3 wallet.
                </p>
                <p>
                  After you've signed the message, you may claim your
                  Clairicature NFT.
                </p>
                <p>
                  Your Clairicature NFT will be minted on the
                  <a href="https://polygon.technology/">Polygon</a> blockchain,
                  and the address from your Web3 wallet that signed the secret
                  code message will be assigned as the owner.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Why Make Clairicature NFTs?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  NFTs are cool!
                  <a
                    href="https://www.essentiallysports.com/nfl-news-odell-beckham-jr-broke-out-nft-worth-2-17-million-during-rams-practice-yesterday/"
                  >
                    OBJ </a
                  >,
                  <a
                    href="https://fortune.com/2022/01/03/eminem-nft-bored-ape-yacht-club"
                  >
                    Eminem </a
                  >, and even
                  <a
                    href="https://www.coindesk.com/markets/2021/08/25/budweiser-buys-beereth-domain-name-for-30-eth-rocket-nft-for-8-eth/"
                  >
                    Budweiser
                  </a>
                  have them!
                </p>
                <p>
                  In all seriousness, this is just for fun, but NFTs do have
                  utility beyond just being speculative overpriced profile
                  pictures for celebrities.
                </p>
                <p>
                  For example, we <em>could</em> use a collection of NFTs like
                  this as part of a secure Web3-based authentication mechanism
                  for internal applications.
                </p>
                <p>
                  You <em>could</em> think of it as a digital employee badge.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Do I Have To Claim My Clairicature
                NFT?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>No.</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Can I Sell My Clairicature NFT?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  Sure! You can list your Clairicature NFT for sale on any NFT
                  marketplace that supports
                  <a
                    href="https://ethereum.org/en/developers/docs/standards/tokens/erc-721/"
                    >ERC-721</a
                  >
                  compliant NFTs on the Polygon blockchain.
                </p>
                <p>
                  <a href="https://opensea.io/">OpenSea</a> is currently the
                  most popular supported marketplace.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >How Much Are Clairicature NFTs Worth?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>Probably nothing.</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Why Am I Receiving An Employee Not Found
                Error?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  The Clairicature NFT smart contract was deployed with
                  Clairicatures for the 44 full-time salaried Clair employees,
                  as reported by Rippling at the time of deployment.
                </p>
                <p>
                  If you are a Clair employee with a Clairicature not included
                  in the collection,
                  <a href="mailto:damian@getclair.com">contact Damian</a> to
                  have it added.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Why Is This Site So Slow?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  This site is hosted on the
                  <a href="https://ipfs.io/"
                    >InterPlanetary File System (IPFS)</a
                  >
                  decentralized file storage network.
                </p>

                <p>There is a performance cost to decentralization.</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >I've Been Waiting For Mint Confirmation For A Long
                Time</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  Minting transactions are sent with a modest gas fee. If there
                  is heavy traffic on the Polygon blockchain, a minting
                  transaction may take a while to be included in a block.
                </p>
                <p>Be patient. The transaction will confirm eventually.</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >My Clairicature Image Is Not Showing On
                OpenSea</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>OpenSea sometimes fails to retrieve images from IPFS.</p>
                <p>
                  If your Clairicature image is not showing on OpenSea, click
                  the refresh metadata button.
                </p>
                <v-img
                  alt="open-sea-refresh-button"
                  src="./open-sea-refresh.png"
                />
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >What Is An NFT?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  NFT stands for non-fungible-token. See the videos below for a
                  better explanation of the details than I can provide.
                </p>
                <ul>
                  <li>
                    <a href="https://www.youtube.com/watch?v=Xdkkux6OxfM"
                      >What Are NFTs and How Can They Be Used in Decentralized
                      Finance? - Finematics</a
                    >
                  </li>
                  <li>
                    <a href="https://www.youtube.com/watch?v=WOxYlBTRncY"
                      >NFT Mania - Hype Or A New Paradigm? - Finematics</a
                    >
                  </li>
                  <li>
                    <a href="https://www.youtube.com/watch?v=mrNOYudaMAc"
                      >NFTs - SNL</a
                    >
                  </li>
                </ul>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >Why Mint On The Polygon Blockchain?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  At the time of writing, most NFT trading activity takes place
                  on the <a href="https://opensea.io/">OpenSea</a> marketplace.
                </p>
                <p>OpenSea currently supports three blockchains.</p>
                <ol>
                  <li><a href="https://ethereum.org/">Ethereum</a></li>
                  <li><a href="https://polygon.technology/">Polygon</a></li>
                  <li><a href="https://www.klaytn.com/">Klaytn</a></li>
                </ol>
                <p class="mt-4">
                  <a href="https://www.youtube.com/watch?v=Yh8cHUB-KoU&t"
                    >Gas</a
                  >
                  on the Ethereum blockchain is egregiously expensive.
                </p>
                <p>
                  Gas on Polygon is significantly cheaper than Ethereum, and it
                  has better developer tooling than Klaytn.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header
                >What Are The Technical Details?</v-expansion-panel-header
              >
              <v-expansion-panel-content>
                <p>
                  The collection of Clairicature NFTs, as well as the claiming
                  application, are <em>mostly</em> decentralized.
                </p>
                <p>
                  The collection of Clairicature NFTs are tracked by an
                  <a
                    href="https://ethereum.org/en/developers/docs/standards/tokens/erc-721/"
                    >ERC-721</a
                  >
                  compliant smart contract deployed at address
                  <code>{{ contractAddress }}</code> on the
                  <a href="https://polygon.technology/">Polygon</a> blockchain.
                </p>
                <p>
                  You can view the verified source code for the smart contract
                  on
                  <a :href="`${polygonScanUrl}/address/${contractAddress}#code`"
                    >Polygonscan.</a
                  >
                </p>
                <p>
                  The smart contract contains a few functions, such as pausing
                  transfers and adding additional employees that may only be
                  called by the address that deployed the contract.
                </p>
                <p>
                  However, the smart contract is structured such that the
                  administrative capabilities can be 'burned' in a
                  cryptographically verifiable way in the future.
                </p>
                <p>
                  The Clairicature NFT images and associated metadata, as well
                  as the front-end for the claiming application (i.e., what
                  you're looking at right now), are all stored on the
                  <a href="https://ipfs.io/"
                    >InterPlanetary File System (IPFS)</a
                  >
                  decentralized file storage network.
                </p>
                <p>
                  The domain for this page (<code>clair.eth</code>) is itself an
                  NFT issued by the
                  <a href="https://ens.domains/">Ethereum Name Service (ENS)</a>
                  decentralized autonomous organization
                  <a
                    href="https://en.wikipedia.org/wiki/Decentralized_autonomous_organization"
                    >(DAO)</a
                  >.
                </p>
                <p>
                  A small backend application runs on a centralized server that
                  assists with the claiming process. This backend application
                  keeps a database of employees with claimed/unclaimed
                  Clairicature NFTs and each employee's associated secret
                  minting code.
                </p>
                <p>
                  The backend application sends the verification email with the
                  secret minting code.
                </p>
                <p>
                  Technically, any address can call the mint function of the NFT
                  smart contract as long as they have a valid secret minting
                  code. However, to execute a mint transaction, you must have
                  <a href="https://www.coingecko.com/en/coins/polygon"
                    >MATIC token</a
                  >
                  in your wallet to pay for
                  <a href="https://www.youtube.com/watch?v=Yh8cHUB-KoU&t"
                    >gas fees</a
                  >. To reduce the barrier to entry for claiming, the backend
                  application also handles calling the smart contract mint
                  function.
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: 'FaqsComponent',
  props: {
    contractAddress: {
      type: String,
      default: '',
    },
    chain: {
      type: String,
      default: '',
    },
  },
  computed: {
    polygonScanUrl() {
      return this.chain === 'matic'
        ? 'https://polygonscan.com'
        : 'https://mumbai.polygonscan.com/'
    },
  },
}
</script>
