<script setup>
const props = defineProps({
  number: Number,
});

function isEven() {
  return props.number % 2 === 0;
}

function getClass() {
  return isEven() ? "border-red" : "border-green";
}
</script>

<template>
  <div class="box" :class="getClass()">
    {{ number }}
  </div>
</template>

<style scoped>
.box {
  display: inline-block;
  padding: 16px 32px;
  margin: 8px;
  background: #121215;
  color: #fff;
  font-size: 24px;
  font-weight: bold;
}

.border-red {
  border-bottom: solid 8px red;
}

.border-green {
  border-bottom: solid 8px green;
}
</style>
