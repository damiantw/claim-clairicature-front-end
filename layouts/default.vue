<template>
  <v-app dark>
    <v-main>
      <v-container>
        <Nuxt />
        <Faqs :contract-address="contractAddress" :chain="chain" />
        <v-img alt="Clair" src="/logo.svg" max-width="275" />
        <Clairicatures :employees="employees" />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      employees: [],
      contractAddress: null,
      chain: null,
    }
  },
  created() {
    this.fetchEmployees()
  },
  methods: {
    async fetchEmployees() {
      const { data } = await this.$axios.get('/employee')
      this.employees = data.employees
      this.contractAddress = data.contractAddress
      this.chain = data.chain
    },
  },
}
</script>
