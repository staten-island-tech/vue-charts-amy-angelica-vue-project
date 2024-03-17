<template>
  <div class="body">
    <div class="title">SQUIRRELS!</div>
    <div class="container">
      <SquirrelCard  v-for="squirrel in squirrels" :key="squirrel.hectare" :squirrel="squirrel"/>
  </div>
  </div>
</template>

<script setup>
 import {array} from '@/stores/store'
import {ref, onBeforeMount} from "vue";
const squirrels = ref("")
async function getSquirrel(){
  let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  squirrels.value = data;
  let eatingsquirrels = data.filter(squirrel => squirrel.eating === true)
  let total = eatingsquirrels.length
  array.cart.push(total)
}
onBeforeMount(()=> {
  getSquirrel();
});



import SquirrelCard from "@/components/SquirrelCard.vue";
</script>

<style  scoped>

  .container {
    display: flex;
  align-items: center;
  text-align: center;
  flex-wrap: wrap;
  justify-content: space-around;
  
}
</style>