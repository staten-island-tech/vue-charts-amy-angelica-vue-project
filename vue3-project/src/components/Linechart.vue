<template>
  <div>
  <Line class="Line" id="my-chart-id" :options="chartOptions" :data="chartData" />
</div>
</template>


<script>

import { Chart as ChartJS, CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend } from 'chart.js'
import { Line } from 'vue-chartjs'

ChartJS.register(CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend)

export default {
  name: 'LineChart',
  components: { Line },
  data() {
    return {
      chartData: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [{
          backgroundColor:  '#85d6ec',
          data: ['Adult', 'Kid'],
        }
        ]
      },
      chartOptions: {
        responsive: false,
      }
    }
  }
}

</script>
<style scoped>
.Line{
  width: 1800px;
  height: 3500px;
}
</style>