<script setup>
import { ref } from "vue";
const name = "World";

const count = ref(0);
</script>

<template>
  <h1>Hello {{ name }}!</h1>

  <button @click="count++">Increment</button>

  <h3>{{ count }}</h3>
</template>

<style></style>
