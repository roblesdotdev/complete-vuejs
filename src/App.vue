<script setup>
import { ref } from "vue";
import Num from "./components/Num.vue";

const numbers = [1, 2, 3, 4];
const selected = ref(-1);

function onSelect(n) {
  selected.value = n;
}

function reset() {
  selected.value = -1;
}
</script>

<template>
  <Num v-for="number in numbers" :number="number" @select="onSelect" />
  <h3 v-if="selected > 0">{{ selected }}</h3>
  <p v-else>Select a number</p>
  <button v-if="selected > 0" @click="reset">Reset</button>
</template>
