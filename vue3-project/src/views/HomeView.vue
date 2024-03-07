<template>
  <div class="body">
    <div class="title">SQUIRRELS!</div>
    <div class="container"  v-for="squirrel in squirrels" :key="squirrel.hectare" :squirrel="squirrel">
      <div class="card">
    <h2>Unique ID: {{ squirrel.unique_squirrel_id }}</h2>
    <h2>Hectare: {{ squirrel.hectare }}</h2>
    <h2>Shift: {{ squirrel.shift }}</h2>
    <h2>Date: {{ squirrel.date }}</h2>
    <h2>Running: {{ squirrel.running }}</h2>
    <h2>Chasing: {{ squirrel.chasing }}</h2>
    <h2>Climbing: {{ squirrel.climbing }}</h2>
    <h2>Eating: {{ squirrel.eating }}</h2>
    <h2>Foragng: {{ squirrel.foraging }}</h2>
    <h2>Kuks: {{ squirrel.kuks }}</h2>
    <h2>Quaas: {{ squirrel.quaas }}</h2>
    <h2>Moans: {{ squirrel.moans }}</h2>
    <h2>Tail Flags: {{ squirrel.tail_flags }}</h2>
    <h2>Tail Twitches: {{ squirrel.tail_twitches }}</h2>
    <h2>Approaches: {{ squirrel.approaches }}</h2>
    <h2>Indifferent: {{ squirrel.indifferent }}</h2>
    <h2>Runs From: {{ squirrel.runs_from }}</h2>
  </div>
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
}
onBeforeMount(()=> {
  getSquirrel();
});

</script>

<style  scoped>
.card {
    font-size: 2rem;
    background-color: white;
    padding: 2%;
    margin: 2rem 2rem;
    border: 3px solid black;
    width: 700px;
    height: 180vh;
  } 
  .container {
  display: flex;
  align-items: center;
  text-align: center;
  flex-wrap: wrap;
  justify-content: space-around;
  flex-direction: column;
  
}
</style>