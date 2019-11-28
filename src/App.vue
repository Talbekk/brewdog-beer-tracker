<template lang="html">

<div>
  <beers-list :beers='beers'></beers-list>
  <beer-label :beer='selectedBeer'></beer-label>
</div>
</template>

<script>

import BeersList from './components/BeersList.vue';
import BeerLabel from './components/BeerLabel.vue';
import {eventBus} from './main.js';

export default {
  name:'app',
  data() {
    return {
      beers: [],
      selectedBeer: null
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

  eventBus.$on('beer-in-hand', (beer) => {
    this.selectedBeer = beer
  })
  },
  components: {
    "beers-list": BeersList,
    "beer-label": BeerLabel
  }
}
</script>

<style lang="css" scoped>
</style>
