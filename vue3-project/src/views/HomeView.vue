<template>
  <div>
    <h1 v-for="eating in data">HELLO</h1>
  </div>
</template>

<script setup>
import {ReferenceError, onBeforeMount} from "vue";
const squirrel = ref("")
async function getSquirrel(){
  let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  squirrel.value = data;
}
onBeforeMount(()=> {
  getSquirrel();
  console.log(data.eating)
});

</script>

<style  scoped>

</style>