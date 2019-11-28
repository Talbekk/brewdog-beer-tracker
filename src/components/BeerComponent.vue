<template lang="html">
  <li v-on:click="grabABeer">{{beer.name}}</li>
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
</style>
