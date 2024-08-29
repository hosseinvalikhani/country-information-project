<script setup lang="ts">
import { onBeforeMount } from "vue";
let countryData: any = [];

onBeforeMount(() => {
  fetch("https://restcountries.com/v3.1/all")
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      countryData = data;
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
  <div
    class="grid grid-cols-1 w-100vh items-center justify-center gap-2 overflow-y-auto sm:grid-cols-2 lg:grid-cols-3 xl:lg:grid-cols-4"
  >
    <div
      v-for="item in countryData"
      :key="item.name.official"
      class="flex gap-x-[20px] items-center bg-blue-100 p-4 w-[250px] h-[80px]"
    >
      <img :src="item.flags.svg" alt="" class="w-8 h-8" />
      <p class="text-left">{{ item.name.official }}</p>
    </div>
  </div>
</template>

<style scoped></style>
