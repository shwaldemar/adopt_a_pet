<template>
  <div class="">
    <h3>This is the Dogs page</h3>
    <b-table striped hover :items="dogs"></b-table>
  </div>
</template>

<script>
import dogs from '@/data/dogs'
export default {
  data: function () {
    return {
      dogs
    }
  }
}
</script>

<style lang="css" scoped>
</style>
