<template>
  <header>


      <nav>
         <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/bar">BarChart</RouterLink> 
        <RouterLink to="/line">LineChart</RouterLink> 
        <RouterLink to="/pie">PieChart</RouterLink>
      </nav>
 
  </header>

  <RouterView />
</template>

<script>
import LineChart from "@/components/Linechart.vue"

export default {
  name: 'App',
  components: { LineChart }
}
</script>