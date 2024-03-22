<template>
    <div v-if="loaded" class="pie">
      <Pie id="my-chart-id" 
      :options="chartOptions" 
      :data="piedata"
      />
    </div>
    <div v-else>
      <h2>Data is loading...</h2>
    </div>
  </template>
  
  <script>

  import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'
  import { Pie } from 'vue-chartjs'
  import { array2 } from '@/stores/store'
  
  ChartJS.register(ArcElement, Tooltip, Legend)
  
  export default {
    name: 'PieChart',
    components: { Pie },
    data: () => ({
      loaded:false,
      piedata: {
          labels: ['Gray', 'Cinnamon', 'White', 'Black'],
          datasets: [
            {
              backgroundColor: ['#808080', '#E5823b', '#f5f5f5', '#000000'],
              data: array2.cart
            }
          ]
        },
    }),
    async mounted(){
      this.loaded = false
      try{
        const res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  
  let get_grays = data.filter(squirrel=> squirrel.primary_fur_color === "Gray")
  let gray = get_grays.length;
  array2.cart[0] = gray
  let get_cinnamons = data.filter(squirrel=> squirrel.primary_fur_color === "Cinnamon")
  let cinnamon = get_cinnamons.length
  array2.cart[1] = cinnamon
  let get_whites = data.filter(squirrel=> squirrel.primary_fur_color === "White")
  let white = get_whites.length
  array2.cart[2] = white
  let get_blacks = data.filter(squirrel=> squirrel.primary_fur_color === "Black")
  let black = get_blacks.length
  array2.cart[3] = black
  this.loaded = true
      }
      catch(e){
        console.error(e)
      }
    }
  }
</script>

<style scoped></style>
  
