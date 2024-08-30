<script setup lang="ts">
interface Props {
  url: string;
  countryName: string;
}
const props = defineProps<Props>();

console.log();
</script>

<template>
  <div
    class="flex gap-x-[20px] items-center p-4 w-[250px] h-[80px] bg-blue-100 rounded-lg hover:bg-blue-300 transition duration-300 ease-in"
  >
    <img :src="props.url" alt="" class="w-8 h-auto" />
    <p class="text-left truncate">{{ props.countryName }}</p>
  </div>
</template>

<style scoped></style>
