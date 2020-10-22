<template>
  <main>
    <header>
      <h1>National Grid Distribution</h1>
    </header>
    <fuel-chart :natGrid="natGrid"></fuel-chart>
    <footer>
      <p>Brought to you by Maria, Paul, Mat and special thanks to our good friend caffeine</p>
    </footer>
  </main>
</template>

<script>
import FuelChart from './components/FuelChart.vue'


export default {
  name: 'app',
  
  data() {
    return {
      natGrid: null
    }
  },

  
  mounted() {
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(response => response.json())
    .then(natGrid => this.natGrid = natGrid.data)
    
  },
  components: {
    "fuel-chart":FuelChart
  }
}
</script>

<style>

</style>