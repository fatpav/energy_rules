<template>
    <GChart
        type="ColumnChart"
        :data="chartData"
        :options="chartOptions"
        />
</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
    data() {
        return {
        chartData: [
            ['fuel', 'type'],
            ['nuclear', 20.4],
            ['hamster', 15],
            ['farts', 80]
        ],
        chartOptions: {
            chart: {
                title: 'Please please work',

            }
        }
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