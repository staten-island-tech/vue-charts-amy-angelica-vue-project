<template>
  <Line :data="data" :options="options" />
</template>
<script>
import { Line } from 'vue-chartjs'
import * as chartConfig from './chartconfig.js'
</script>