<template lang="html">
  <li v-on:click="grabABeer">
    <h3>{{beer.name}}</h3>
    <p>{{beer.abv}}</p>
    <p>{{beer.tagline}}</p>
    <img class="beer-icon" src="../../public/beer_icon.svg"/>
  </li>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beer-component',
  props: ['beer'],
  methods: {
    grabABeer() {
      eventBus.$emit('beer-in-hand', this.beer);
    }
  }
}
</script>

<style lang="css" scoped>

.beer-icon {
  max-width: 3em;
}
</style>
