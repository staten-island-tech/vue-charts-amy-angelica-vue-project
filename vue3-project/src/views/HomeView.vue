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
  let runningsquirrels = data.filter(squirrel => squirrel.running === true)
  let run = runningsquirrels.length
  array.cart[0] = run
  let chasingsquirrels = data.filter(squirrel => squirrel.chasing === true)
  let chase = chasingsquirrels.length
  array.cart[1] = chase
  let climbingsquirrels = data.filter(squirrel => squirrel.climbing === true)
  let climb = climbingsquirrels.length
  array.cart[2] = climb
  let eatingsquirrels = data.filter(squirrel => squirrel.eating === true)
  let eat = eatingsquirrels.length
  array.cart[3] = eat
  let foragingsquirrels = data.filter(squirrel => squirrel.foraging === true)
  let forage = foragingsquirrels.length
  array.cart[4] = forage
  let kukssquirrels = data.filter(squirrel => squirrel.kuks === true)
  let kuk = kukssquirrels
  array.cart[5] = kuk
  
  
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