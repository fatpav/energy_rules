<template>

<section v-if='natGrid'>
    <h1>Percentage of national grid by fuel type in the last 30 minutes since {{ timefixer() }}:</h1>
    <GChart
        type="PieChart"
        :data="chartData"
        :options="chartOptions"
        />
        
</section>        
</template>

<script>
import { GChart } from 'vue-google-charts'
import moment from 'moment'

export default {
    data() {
        return {
        chartOptions: {
            height: 500,
            width:1000,
            is3D: true,
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
        },
    },    
    methods: {
        timefixer() {
            const str = `${ this.natGrid.from }`;
            const date = moment(str);
            const dateComponent = date.utc().format('YYYY-MM-DD');
            const timeComponent = date.utc().format('HH:mm:ss');
            return `${dateComponent} at ${timeComponent}`
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