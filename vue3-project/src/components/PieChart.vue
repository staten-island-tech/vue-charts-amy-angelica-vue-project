<template>
    <div class="pie">
      <Pie id="my-chart-id" 
      :options="chartOptions" 
      :data="piedata"/>
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
    data() {
      return {
        piedata: {
          labels: ['Gray', 'Cinnamon', 'White', 'Black'],
          datasets: [
            {
              backgroundColor: ['#808080', '#E5823b', '#f5f5f5', '#000000'],
              data: array2.cart
            }
          ]
        },
        loaded: false,
        chartOptions: {
          responsive: true
        }
      }
    }
  }
  </script>
  
   <style>
  .pie{
    height: 80vh;
    text-align: center;
    align-items: center;
    align-content: center;
    overflow: hidden;
  }

  </style>