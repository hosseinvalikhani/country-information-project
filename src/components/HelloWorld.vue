<script setup lang="ts">
import { ref } from "vue";
const countriesData = ref(null);

fetch("https://restcountries.com/v3.1/all")
  .then((response) => response.json())
  .then((data) => (countriesData.value = data.data));

console.log(countriesData);

const products = ref(null);
fetch("https://testapi.jasonwatmore.com/products")
  .then((response) => response.json())
  .then((data) => (products.value = data));

console.log(products);
</script>

<template>
  {{ products }}
  <h1 class="text-3xl font-bold underline">Hello world!</h1>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
