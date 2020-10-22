<template>

<section v-if='natGrid'>
    <h1>Check my badass chart!</h1>
    <GChart
        type="ColumnChart"
        :data="chartData"
        :options="chartOptions"
        />
        
</section>        
</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
    data() {
        return {
        chartOptions: {
            chart: {
                title:'Please please work',
                subtitle:'A study of some things'
                }
            }
        }
    },
    computed: {
        chartData: function() {
            return [
                ["Fuel", "Percentage"],
                ...this.natGrid.generationmix.map(pair => {
                    return [pair.fuel, pair.perc]
                })
            ]
        }
    },
    name: 'fuel-chart',
    props: ['natGrid'],
    components: {
        GChart,
    }
}


</script>

<style>

</style>