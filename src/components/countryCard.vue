<script setup lang="ts">
interface Props {
  url: string;
  countryName: string;
  capital: string[];
  region: string;
  population: number;
}
const props = defineProps<Props>();

console.log();
</script>

<template>
  <div
    class="flex flex-col gap-x-[20px] items-start justify-around p-4 w-[250px] h-[180px] bg-blue-100 rounded-lg hover:bg-blue-300 transition duration-300 ease-in"
  >
    <div class="flex gap-x-[20px] items-start">
      <img :src="props.url" alt="" class="w-12 h-auto" />
      <p class="text-left max-w-[150px] truncate">{{ props.countryName }}</p>
    </div>
    <div class="flex flex-col items-start gap-2 w-full">
      <p class="text-left truncate">Population: {{ props.population }}</p>
      <p class="text-left truncate">Capital: {{ props.capital? props.capital[0]: "" }}</p>
      <p class="text-left truncate">Region: {{ props.region }}</p>
    </div>
  </div>
</template>

<style scoped></style>
