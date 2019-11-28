<template lang="html">

</template>

<script>
export default {
  data() {
    return {
      beers: []
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)
    console.log(this.beers);
  }
}
</script>

<style lang="css" scoped>
</style>
