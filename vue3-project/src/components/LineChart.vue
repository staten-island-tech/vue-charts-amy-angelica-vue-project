<template>
  <div>
  <Line class="Line" id="my-chart-id" :options="chartOptions" :data="linedata" />
</div>
</template>


<script>

import { Chart as ChartJS, CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend } from 'chart.js'
import { Line } from 'vue-chartjs'
import { array3 } from '@/stores/store'

ChartJS.register(CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend)

export default {
  name: 'LineChart',
  components: { Line },
  data() {
    return {
      linedata: {
        labels:['Gray', 'Cinnamon', 'White', 'Black'],
        datasets: [{
          backgroundColor:  '#85d6ec',
          data:array3.cart,
        }
        ]
      },
      loaded: false,
      chartOptions: {
        responsive: true,
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