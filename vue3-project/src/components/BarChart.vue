<template>
  <div class ="bar">
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />
  </div>
  </template>
  
  <script>
  import { Bar } from 'vue-chartjs'
  import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
  import {array} from '@/stores/store'
  
  ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)
  
  export default {
    name: 'BarChart',
    components: { Bar },
    data() {
      return {
        chartData: {
          labels: [ 'Running', 'Chasing','Climbing','Eating','Foraging','Kuks','Quaas', 'Moans', 'Tail Flags','Tail Twtiches', 'Approaches','Indifferent','Runs from' ],
          datasets: [ { 
            backgroundColor: '#FF69B4',
            label: 'Squirrels',
            data: array.cart}]
          
        },
        chartOptions: {
          responsive: true
        },
        async mounted (){}
      }
    }
  }

  </script>

  