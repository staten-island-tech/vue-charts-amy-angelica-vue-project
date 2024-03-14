<template>
  <div class="Line">
  <Line id="my-chart-id" :options="chartOptions" :data="chartData" />
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
          backgroundColor: '#f87979',
          data: [40, 39, 10, 40, 39, 80, 40]
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
