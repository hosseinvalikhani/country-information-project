<script setup lang="ts">
import { onBeforeMount } from "vue";
let countryData: any = [];

onBeforeMount(() => {
  fetch("https://restcountries.com/v3.1/all")
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      countryData = data.slice(1, 11);
      console.log(countryData);
    })
    .catch(function (error) {
      console.log(error);
    });

  //   fetch(url, {
  //   headers: {
  //     "x-api-key": api_key,
  //   },
  // })
  //   .then((response) => {
  //     return response.json();
  //   })
  //   .then((data) => {
  //     let imagesData: any = data;
  //     console.log(imagesData);
  //   })
  //   .catch(function (error) {
  //     console.log(error);
  //   });
});
</script>

<template>
  <h1 class="text-3xl font-bold underline">Hello world!</h1>
  <img src="" alt="" />
  <div
    v-for="item in countryData"
    class="flex flex-col items-center justify-center"
    :key="item.cca3"
  >
    <div class="flex">
      <img :src="item.flags.svg" alt="" class="w-8 h-8" :key="item.cca3" />
      <p :key="item.cca3">{{ item.name.official }}</p>
    </div>
  </div>
</template>

<style scoped></style>
