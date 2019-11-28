<template lang="html">

<div id="listContainer">
  <ul>
    <beer-component v-for="(beer, index) in beers" :beer='beer' :favoriteFilter="favoriteFilter" :key='index'></beer-component>
  </ul>
</div>
</template>

<script>
import BeerComponent from './BeerComponent.vue';

export default {
  name: 'beers-list',
  props: ['beers', 'favoriteFilter'],
  components: {
    "beer-component": BeerComponent
  }
}


</script>

<style lang="css" scoped>

#listContainer ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>
