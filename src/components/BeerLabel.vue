<template lang="html">
<div v-if='beer'>
  <h3>{{beer.name}}</h3>
  <p>Tagline: {{beer.tagline}}</p>
  <p>First Brewing: {{beer.first_brewed}}</p>
  <p>Description: {{beer.description}}</p>
  <p>ABV: {{beer.abv}}%</p>
  <img class="beer-icon" :src="beer.image_url"/>
</div>
</template>

<script>
export default {
  name: 'beer-label',
  props: ['beer']
}
</script>

<style lang="css" scoped>

.beer-icon {
  max-width: 3em;
}
</style>
