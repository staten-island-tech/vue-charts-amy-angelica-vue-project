<template>
    <BarChart />
</template>

<script setup>
import BarChart from '@/components/BarChart.vue';
import {array} from '@/stores/store'
import {ref, onBeforeMount} from "vue";
const squirrels = ref("")
async function getSquirrel(){
  let res = await fetch("https://data.cityofnewyork.us/resource/vfnx-vebw.json");
  let data = await res.json();
  squirrels.value = data;
  bruh(data)
}
 function bruh(data){
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
  let kuk = kukssquirrels.length
  array.cart[5] = kuk

  let quaassquirrels = data.filter(squirrel => squirrel.quaas === true)
  let qua = quaassquirrels.length
  array.cart[6] = qua

  let moanssquirrels = data.filter(squirrel => squirrel.moans === true)
  let moan = moanssquirrels.length
  array.cart[7] = moan

  let tailflags = data.filter(squirrel => squirrel.tail_flags === true)
  let tailflag = tailflags.length
  array.cart[8] = tailflag

  let tailtwitches = data.filter(squirrel => squirrel.tail_twitches === true)
  let tailtwitch = tailtwitches.length
  array.cart[9] = tailtwitch

  let approaches = data.filter(squirrel => squirrel.tail_twitches === true)
  let approach = approaches.length
  array.cart[10] = approach

  let indifferents = data.filter(squirrel => squirrel.indifferent === true)
  let indifferent = indifferents.length
  array.cart[11] = indifferent

  let runsfrom = data.filter(squirrel => squirrel.runs_from === true)
  let ruuun = runsfrom.length
   array.cart[12] =ruuun
}
onBeforeMount(()=> {
  getSquirrel();
});
</script>