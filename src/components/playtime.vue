<template>
  
</template>

<script>

import natGrid from '@/app.vue'

export default {
    methods: {
      dataHandler: function() {
        return natGrid.data.generationmix.map(pair => {
        return chartData = [pair.fuel, pair.perc]
        })
      }
    }

}
</script>

<style>

</style>