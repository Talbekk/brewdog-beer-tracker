<template lang="html">

<div id="listContainer">
  <h1>Beers List:</h1>
  <ul>
    <beer-component v-for="(beer, index) in beers" :beer='beer' :key='index'></beer-component>
  </ul>
</div>
</template>

<script>
import BeerComponent from './BeerComponent.vue';

export default {
  name: 'beers-list',
  props: ['beers'],
  components: {
    "beer-component": BeerComponent
  }
}

</script>

<style lang="css" scoped>
</style>
