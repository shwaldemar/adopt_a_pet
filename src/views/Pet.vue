<template>
  <div class="">
    <h1>{{ animal.name  }} ({{$route.params.species}})</h1>
    <h4>is a {{animal.age }} year old {{animal.gender}} {{animal.color}}
    {{animal.breed }} {{ animal.species}}.
    {{animal.name}} weighs {{animal.weight}} llbs & is {{animal.notes}}.</h4>
  </div>

</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState(['cats', 'dogs'])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>

<style lang="css" scoped>
</style>
