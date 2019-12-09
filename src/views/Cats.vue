<template>
  <div class="">
    <h3>This is the Cats page</h3>
    <b-table striped hover :items="cats"></b-table>
  </div>
</template>

<script>
import cats from '@/data/cats'
export default {
  data: function () {
    return {
      cats
    }
  }
}
</script>

<style lang="css" scoped>
</style>
