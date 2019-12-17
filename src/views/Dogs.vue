<template>
  <div class="">
    <h1>Dogs for adoption</h1>
    <b-table striped hover :items="dogs">
      <template v-slot:cell(name)="data">
        <!-- `data.value` is the value after formatted by the Formatter -->
        <router-link :to="`/pets/dogs/${data.index}`">
          {{ data.value }}
        </router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import { mapState } from 'vuex'

// import dogs from '@/data/dogs' // using mapstate from vuex to import data instead.

export default {
  data: function () {
    return {}
  },
  computed: {
    ...mapState(['dogs'])
  }
}
</script>

<style lang="css" scoped>
</style>
