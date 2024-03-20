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
        labels: [10.5, 10.6, 10.7, 10.8, 10.9,],
        datasets: [{
          backgroundColor:  '#85d6ec',
          data: [10.5, 10.6],
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