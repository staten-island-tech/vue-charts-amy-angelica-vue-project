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
            data: [false, true, false, true, true, true, true, true, true, true, true, true, true, true, true] } ]
          
        },
        chartOptions: {
          responsive: true
        },
        methods: {
          async fetchData(){
          let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
          let data = await res.json();
          squirrels.value = data;
          }
        },
        mounted(){
          this.fetchData
        }
      }
    }
  }
const draft = [
  {
    poop: true,
  },
  {
    poop: true,
  },
  {
    poop: true,
  },
  {
    poop: true,
  },
  {
    poop: false,
  },
]
function poop(){
for (let i =0; i > draft.length; i++){
const add = Number(poop);
console.log (add === 0);
console.log (add === 1);
}}
poop()
  </script>

  