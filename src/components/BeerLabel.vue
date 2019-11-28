<template lang="html">
<div v-if='beer'>
  <p>{{beer.name}}</p>
</div>
</template>

<script>
export default {
  name: 'beer-label',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
