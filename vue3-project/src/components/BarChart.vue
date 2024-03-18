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
            backgroundColor: '#f87979',
            data: array.cart}]
          
        },
        chartOptions: {
          responsive: true
        },
        methods: {

        }
      }
    }
  }
//   const drafts = [
//   {
//     poop: true,
//   },
//   {
//     poop: true,
//   },
//   {
//     poop: true,
//   },
//   {
//     poop: true,
//   },
//   {
//     poop: false,
//   },
// ]
// function bruh(){
// let message = 0;
// drafts.forEach(function(draft){
//   if (draft.poop === true){
//     message += Number(draft.poop)
//     return message
//   }
//   console.log(message)
// })}

  </script>

  