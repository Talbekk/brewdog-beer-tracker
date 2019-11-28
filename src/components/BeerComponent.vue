<template lang="html">
  <li  v-if="this.status || (!this.status && !favoriteFilter)">
    <h3>{{beer.name}}</h3>
    <p>{{beer.abv}}</p>
    <p>{{beer.tagline}}</p>
    <img class="beer-icon" src="../../public/beer_icon.svg"/>
    <input type="checkbox" id="favorite" v-model="status">
    <label for="favorite" v-if="!status">Add to favorites</label>
    <button type="button" v-on:click="grabABeer">View Info</button>
  </li>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beer-component',
  props: ['beer', 'favoriteFilter'],
  data() {
    return {
      status: false
    }
  },
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
