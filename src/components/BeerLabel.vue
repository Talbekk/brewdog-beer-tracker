<template lang="html">
<section id="header-right" v-if='beer'>
  <div id="label-right">
  <h3>{{beer.name}}</h3>
  <p>Tagline: {{beer.tagline}}</p>
  <p>First Brewing: {{beer.first_brewed}}</p>
  <p>Description: {{beer.description}}</p>
  <p>ABV: {{beer.abv}}%</p>
  </div>
  <img class="beer-icon" :src="beer.image_url"/>
</section>
</template>

<script>
export default {
  name: 'beer-label',
  props: ['beer']
}
</script>

<style lang="css" scoped>


.beer-icon {
  max-width: 10em;
  max-height: 10em;
  padding: 2em;
}

#header-right{
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
  border: 2px solid #336666;
  border-radius: 2%;
}

</style>
