<template>
  <div class="cotainer">
    <h1>This is an about page</h1>
  </div>

<script setup>
import {ref,onMounted} from "vue";
const pokemon =ref ("");
async function getPokemon(){
  let res = await fetch("https://data.cityofnewyork.us/d/fak5-wcft");
  let data = await res.json();
  pokemon.value= data;

}

onBeforeMount(()=>{
  getPokemon();
});
</script>
</template>

<style>

</style>
