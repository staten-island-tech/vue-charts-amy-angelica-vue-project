<template>
     <div class ="bar">
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />
  </div>
  </template>
  
  <script lang="ts">
  import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
  import { Pie } from 'vue-chartjs'
  import * as chartConfig from ''
  
  ChartJS.register()
  
  export default {
    name: 'App',
    components: {
      Pie
    },
    data() {
      return chartConfig
    }
  }
  </script>
  