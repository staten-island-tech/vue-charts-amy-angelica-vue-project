<template>
  <div class="body">
    <div class="title">SQUIRRELS!</div>
    <div class="container">
      <SquirrelCard  v-for="squirrel in squirrels" :key="squirrel.hectare" :squirrel="squirrel"/>
  </div>
  </div>
</template>

<script setup>

import {ref, onBeforeMount} from "vue";
const squirrels = ref("")
async function getSquirrel(){
  let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  squirrels.value = data;

  let get_grays = data.filter(squirrel=> squirrel.running === "Gray")
  let gray = get_grays.length
  array2.cart[0] = gray
  let get_cinnamons = data.filter(squirrel=> squirrel.running === "Cinnamon")
  let cinnamon = get_cinnamons.length
  array2.cart[1] = cinnamon
  let get_whites = data.filter(squirrel=> squirrel.running === "White")
  let white = get_whites.length
  array2.cart[2] = white
  let get_blacks = data.filter(squirrel=> squirrel.running === "Black")
  let black = get_blacks.length
  array2.cart[3] = black


}
onBeforeMount(()=> {
  getSquirrel();
})

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