<template lang="html">
  <li v-on:click="grabABeer">{{beer.name}}</li>
</template>

<script>

export default {
  name: 'beer-component',
  props: ['beer'],
  methods: {
    grabABeer() {
      console.log(this.beer);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
