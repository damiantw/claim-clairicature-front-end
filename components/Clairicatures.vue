<template>
  <v-row>
    <v-col
      v-for="employee in employees"
      :key="employee.id"
      class="d-flex child-flex"
      cols="4"
    >
      <v-img :alt="employee.name" :src="employee.image" aspect-ratio="1">
        <v-badge
          :value="employee.claimed"
          content="Claimed"
          color="green"
          offset-y="75"
          offset-x="-25"
        ></v-badge>
        <template #placeholder>
          <v-row class="fill-height ma-0" align="center" justify="center">
            <v-progress-circular
              indeterminate
              color="grey lighten-5"
            ></v-progress-circular>
          </v-row>
        </template>
      </v-img>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: 'ClairicaturesComponent',
  props: {
    employees: {
      type: Array,
      default: () => [],
    },
  },
}
</script>
