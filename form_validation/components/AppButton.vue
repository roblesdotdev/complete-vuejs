<script setup>
const props = defineProps({
  text: String,
  background: String,
  color: String,
  disabled: Boolean,
});
</script>

<template>
  <button :disabled="disabled" :style="{ background, color }">
    {{ text }}
  </button>
</template>

<style scoped>
button:disabled {
  opacity: 0.6;
}

button {
  background: none;
  color: black;
  border: none;
  border-radius: 5px;
  padding: 12px 32px;
  font-size: 16px;
  cursor: pointer;
  width: 100%;
  margin-top: 10px;
  text-transform: uppercase;
}

button:hover {
  filter: brightness(125%);
}

button:hover:disabled {
  filter: none;
}
</style>
