<script setup>
import { ref } from "vue";
const name = ref("World");
</script>

<template>
  <input v-model="name" />
  <p>Hello {{ name }}!</p>
</template>

<style>
.red {
  color: red;
}
.blue {
  color: blue;
}
</style>
