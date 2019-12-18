<template>
  <div class="cat-view-container">
    <h1>Cats for adoption</h1>
    <b-table striped hover :items="cats">
      <template v-slot:cell(name)="data">
        <!-- `data.value` is the value after formatted by the Formatter -->

        <router-link class="pet-view-container" :to="`/pets/${species}/${data.index}`">
          {{ data.value }}
        </router-link>
      </template>
    </b-table>
  </div>
</template>

<script type="text/javascript">
  export default {
    props: {
      species: String,
      pets: Array
    }
  }
</script>
