<script setup lang="ts">
import { onMounted, ref } from "vue";
import CountryCard from "./countryCard.vue";
interface Country {
  name: {
    official: string;
  };
  cca3: string;
  flags: {
    svg: string;
    png: string;
  };
  capital: string[];
  region: string;
  population: number;
}

let countryData = ref<Country[]>([]);

onMounted(() => {
  fetch("https://restcountries.com/v3.1/all")
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      countryData.value = data;
      console.log(countryData);
      console.log(countryData.value)

    })
    .catch(function (error) {
      console.log(error);
    });
});

function countryCall() {
  console.log(countryName);
}
</script>

<template>
  <h1 class="text-3xl font-bold underline">Hello world!</h1>

  <div
    class="grid grid-cols-1 w-100vh items-center justify-center gap-2 overflow-y-auto sm:grid-cols-2 lg:grid-cols-3 xl:lg:grid-cols-4"
  >
    <CountryCard
      v-for="item in countryData"
      :key="index"
      :url="item.flags.svg"
      :country-name="item.name.official"
      :population="item.population"
      :capital="item.capital"
      :region="item.region"
    ></CountryCard>
  </div>
</template>

<style scoped></style>
