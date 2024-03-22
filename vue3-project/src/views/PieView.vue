<template>
    <PieChart/>
</template>

<script setup>
  import PieChart from '@/components/PieChart.vue'; 
//   import { array2 } from "@/stores/store";
// import {ref, onBeforeMount} from "vue";
// const squirrels = ref("")
// async function getSquirrel(){
//   let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
//   let data = await res.json();
//   squirrels.value = data;

//   let get_grays = data.filter(squirrel=> squirrel.primary_fur_color === "Gray")
//   let gray = get_grays.length;
//   array2.cart[0] = gray
//   let get_cinnamons = data.filter(squirrel=> squirrel.primary_fur_color === "Cinnamon")
//   let cinnamon = get_cinnamons.length
//   array2.cart[1] = cinnamon
//   let get_whites = data.filter(squirrel=> squirrel.primary_fur_color === "White")
//   let white = get_whites.length
//   array2.cart[2] = white
//   let get_blacks = data.filter(squirrel=> squirrel.primary_fur_color === "Black")
//   let black = get_blacks.length
//   array2.cart[3] = black


// }
// onBeforeMount(()=> {
//   getSquirrel();
// })
</script>

<style>

</style>