<template lang="html">
<h1>Beers List:</h1>
<div id="list-container">
  <ul>
    <beer-component v-for="(beer, index) in beers" :beer="beer" :key="index"/>
  </ul>
</div>
</template>

<script>
export default {
  name: 'beers-list',
  props: ['beers']
}
</script>

<style lang="css" scoped>
</style>
