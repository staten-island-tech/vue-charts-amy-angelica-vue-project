<template>
  <Line :data="data" :options="options" />
</template>


<script lang="">

import { Line } from 'vue-chartjs'
import { Chart as CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend} from 'chart.js'

ChartJS.register( CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend)

export default {
  name: 'App',
  components: { Line },
  data() {
    return {
      chartData: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
      datasets: [
          {
          label: 'Data One',
          backgroundColor: '#f87979',
          data: [40, 39, 10, 40, 39, 80, 40]
          }
        ]
      }
    }
  }
}
</script>