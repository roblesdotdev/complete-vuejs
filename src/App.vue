<script setup>
import Num from "./components/Num.vue";

const numbers = [1, 2, 3, 4];
</script>

<template>
  <Num v-for="number in numbers" :number="number" />
</template>
