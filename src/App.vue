<template>
  <h1>What up, team!</h1>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      natGrid: []
    }
  },
  mounted() {
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(response => response.json())
    .then(natGrid => this.natGrid = natGrid)
  }

}
</script>

<style>

</style>