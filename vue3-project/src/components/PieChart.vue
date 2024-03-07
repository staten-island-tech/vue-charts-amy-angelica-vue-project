<template>
     <div class ="pie">
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />
  </div>
  </template>
  
  <script>  
  import { Pie } from 'vue-chartjs'
  import { Chart as ChartJS, ArcElement, Tooltip, Legend  } from 'chart.js';
  ChartJS.register(ArcElement, Tooltip, Legend);
    
  export default {
    name: 'Pie',
    components: { Pie },
    data() {
      return {
        chartData: {
          labels: [ 'January', 'February', 'March', 'Angela' ],
          datasets: [ { 
            backgroundColor: '#f87979',
            data: [40, 20, 12, 35] } ]
          
        },
        chartOptions: {
          responsive: true
        }
      }
    }
  }
  </script>
  