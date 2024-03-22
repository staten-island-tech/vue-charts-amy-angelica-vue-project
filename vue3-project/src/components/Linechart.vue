<template>
    <div v-if="loaded"class="Line">
    <Line id="my-chart-id" 
    :options="chartOptions" 
    :data="linedata" />
  </div>
  <div v-else>
    <h2>Data is loading...</h2>
  </div>
  </template>
  
  
  <script>
  
  import { Chart as ChartJS, CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend } from 'chart.js'
  import { Line } from 'vue-chartjs'
  import { array3 } from '@/stores/store'
  
  ChartJS.register(CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend)
  
  export default {
    name: 'LineChart',
    components: { Line },
    data: () => ({
        loaded: false,
        linedata: {
          labels:['Gray', 'Cinnamon', 'White', 'Black'],
          datasets: [{
            label: 'Squirrel',
            backgroundColor:  '#85d6ec',
            data:array3.cart,
          }]
        },
    }),
    async mounted(){
      this.loaded = false
      try{
        const res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  
  let get_grays = data.filter(squirrel=> squirrel.primary_fur_color === "Gray")
  let gray = get_grays.length;
  array3.cart[0] = gray
  let get_cinnamons = data.filter(squirrel=> squirrel.primary_fur_color === "Cinnamon")
  let cinnamon = get_cinnamons.length
  array3.cart[1] = cinnamon
  let get_whites = data.filter(squirrel=> squirrel.primary_fur_color === "White")
  let white = get_whites.length
  array3.cart[2] = white
  let get_blacks = data.filter(squirrel=> squirrel.primary_fur_color === "Black")
  let black = get_blacks.length
  array3.cart[3] = black
  this.loaded = true
      }
      catch(e){
        console.error(e)
      }
    }
  }
</script>

<style scoped></style>