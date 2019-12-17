<template>
  <div class="">
    <h1>Cats for adoption</h1>
    <b-table striped hover :items="cats">
      <template v-slot:cell(name)="data">
        <!-- `data.value` is the value after formatted by the Formatter -->

        <router-link :to="`/pets/cats/${data.index}`">
          {{ data.value }}
        </router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import { mapState } from 'vuex'
// import cats from '@/data/cats' //using mapstate from vuex instead.

export default {
  data: function () {
    return {}
  },
  computed: {
    ...mapState(['cats'])
  }
}
</script>

<style lang="css" scoped>
</style>
