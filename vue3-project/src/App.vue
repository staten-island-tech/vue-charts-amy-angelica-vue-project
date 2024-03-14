<template>
  <header>


      <nav>
         <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/bar">BarChart</RouterLink> 
      </nav>
 
  </header>

  <RouterView />
</template>

<script>
import LineChart from "@/components/LineChart.vue"

export default {
  name: 'App',
  components: { LineChart }
}
</script>