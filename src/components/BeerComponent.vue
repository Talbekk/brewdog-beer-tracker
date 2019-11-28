<template lang="html">
  <li class="list-element" v-if="this.status || (!this.status && !favoriteFilter)">

    <div class="article-top">
    <h3>{{beer.name}}</h3>
    <input type="checkbox" id="favorite" v-model="status">
    <label for="favorite" v-if="!status">Add to favorites</label>
    </div>

    <div class="article-bottom">
      <div class="article-right">
        <p>ABV: {{beer.abv}}%</p>
        <p>"{{beer.tagline}}"</p>
        <button type="button" v-on:click="grabABeer">View Info</button>
      </div>

      <img class="beer-icon" src="../../public/beer_icon.svg"/>

    </div>

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

li {
  display: flex;
  flex-direction: column;
  margin: 0.5em;
  padding: 1em;
  max-width: 40%;
  border: 2px solid #669999;
  border-radius: 2%;
}

.article.top {
  border: 1px dotted #ccc;
  display: flex;
  flex-direction: row;
}

.article.bottom {
  border: 1px dotted #ccc;
  display: flex;
  flex-direction: row-reverse;
}

.article-right {
  border: 1px dotted #ccc;
  display: flex;
  flex-direction: column;
  max-width: 40%;
  flex-wrap: wrap;
}

.beer-icon {
  width: 3em;
  padding: 1em;
}

h3 {
  border: 1px dotted #ccc;
  font-family: 'Open Sans', sans-serif;
  font-weight: 800;
  display: flex;
  flex-wrap: wrap;
  max-width: 200px;
}
</style>
