<template lang="html">
  <li>{{beer.name}}</li>
</template>

<script>

export default {
  name: 'beer-component',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
