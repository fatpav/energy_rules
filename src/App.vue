<template>
  <fuel-chart :chartData="chartData"></fuel-chart>  
</template>

<script>
import FuelChart from './components/FuelChart.vue'

export default {
  name: 'app',
  

  data() {
    return {
      natGrid: [],
      chartData: []
    }
  },

  // computed: {
  //   dataHandler: function() {
  //     return natGrid.data.generationmix.map(pair => {
  //      return chartData = [pair.fuel, pair.perc]
    //   })
    // }
  // },

  mounted() {
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(response => response.json())
    .then(natGrid => this.natGrid = natGrid)
  },
  components: {
    "fuel-chart":FuelChart
  }
}
</script>

<style>

</style>