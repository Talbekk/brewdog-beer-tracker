<template lang="html">
<li class="list-element" v-if="this.status || (!this.status && !favoriteFilter)">
  <div class="article">
    <img class="beer-icon" :src="beer.image_url"/>
    <h3>{{beer.name}}</h3>
    <p>"{{beer.tagline}}"</p>
    <p>ABV: {{beer.abv}}%</p>
    <p></p>
    <div class="my-checkbox">
      <input type="checkbox" id="favorite" v-model="changeStatus">
      <label for="favorite"></label>
    </div>
    <button type="button" v-on:click="grabABeer">View Info</button>
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
  computed: {
    teamLineUp: function () {
      return this.pokemons.filter(pokemon => pokemon.isChosen);
    }
  }
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
  max-width: 20%;
  border: 2px solid #669999;
  border-radius: 30%;
  flex-grow: 1;
}

.article {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}

.beer-icon {
    max-width: 10em;
    max-height: 8em;
    padding: 0.5em;
}

h3 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 800;
  display: flex;
  flex-wrap: wrap;
  max-width: 200px;
}

button {
  background-color: grey;
  border: none;
  color: white;
  padding: 12px 24px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}

.my-checkbox input[type="checkbox"] {
  display: none;
}
.my-checkbox input[type="checkbox"]+label {
  background: url('../../public/abv-logo.svg') no-repeat;
  width: 2em;
  height: 2em;
  padding: 2em;
}
.my-checkbox input[type="checkbox"]:checked + label {
  background: url('../../public/beer_icon.svg') no-repeat;
  width: 1em;
  height: 1em;
  padding: 1em;
}

</style>
