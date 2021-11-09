<script setup>
import { ref } from "vue";
const name = "World";
const ages = [32, 23, 39, 19];

const count = ref(0);

function isEven() {
  return count.value % 2 === 0;
}
</script>

<template>
  <h1>Hello {{ name }}!</h1>

  <button @click="count++">Increment</button>

  <h3>{{ count }}</h3>
  <p v-if="isEven()">Even</p>
  <p v-else>Odd</p>

  <div v-for="age in ages">
    {{ age }}
  </div>
</template>

<style></style>
