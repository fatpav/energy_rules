<template>
  <main>
    <header>
      <h1>National Grid Distribution</h1>
      <a href="https://www.youtube.com/watch?v=R-FxmoVM7X4"> <img src="https://b.kisscc0.com/20180813/iee/kisscc0-electric-potential-difference-high-voltage-compute-danger-high-voltage-alt-1-5b723599e45913.2974827115342114819353.png" alt="Electricity Flash Lightning Danger Warning"> </a>
    </header>
      <article>
        <fuel-chart :natGrid="natGrid"></fuel-chart>
      </article>
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
body {
  margin: 0;
}

main {
  display: grid;
  grid-template-rows: 100px auto 100px;
  min-height: 100vh;
  grid-template-areas: 
  'header'
  'article'
  'footer';
}

header {
  grid-area: header;
  display: flex;
  justify-content: space-between;

  background-color: navy;
  color: white;
  align-items: center;
}

header > a > img {
  height: 100px;
  width: auto;
  padding: 0 0 10px 0;
}

h1 {
  padding:10px;
}

article {
  grid-area: article;
}

footer {
  grid-area: footer;
  background-color: navy;
  color: white;
  align-items: center;
}

footer > p {
  padding: 10px;
}


</style>