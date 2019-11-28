<template lang="html">

<div id="listContainer">
  <h1>Beers List:</h1>
  <button type="button" v-on:click="favoriteFilter = !favoriteFilter">{{ favoriteFilter ? "Show All" : "Show Favorites" }}</button>
  <ul>
    <beer-component v-for="(beer, index) in beers" :beer='beer' :favoriteFilter="favoriteFilter" :key='index'></beer-component>
  </ul>
</div>
</template>

<script>
import BeerComponent from './BeerComponent.vue';

export default {
  name: 'beers-list',
  props: ['beers'],
  data() {
    return {
    favoriteFilter: false
  }
  },
  components: {
    "beer-component": BeerComponent
  }
  //   filterByFavorite() {
  //   if (this.favoriteFilter === true){
  //   this.beers.filter(beer => beer.status)
  //   console.log(this.beers);
  // }
    // }
  // }
}

</script>

<style lang="css" scoped>
</style>
