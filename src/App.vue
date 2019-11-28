<template lang="html">

<div>
  <beers-list :beers='beers'/>
</div>
</template>

<script>

import BeersList from './components/BeersList.vue';

export default {
  name:'app',
  data() {
    return {
      beers: []
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)
  },
  components: {
    "beers-list": BeersList
  }
}
</script>

<style lang="css" scoped>
</style>
