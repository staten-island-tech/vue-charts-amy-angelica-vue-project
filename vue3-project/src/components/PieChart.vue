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
  
  ChartJS.register(ArcElement, Tooltip, Legend)
  
  export default {
    name: 'PieChart',
    components: { Pie },
    data() {
      return {
        piedata: {
          labels: ['Gray', 'Cinnamon', 'White', 'AngularJs'],
          datasets: [
            {
              backgroundColor: ['#808080', '#E5823b', '#f5f5f5', '#DD1B16'],
              data: [40, 20, 80, 10]
            }
          ]
        },
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