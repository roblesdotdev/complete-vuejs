<script setup>
const props = defineProps({
  number: Number,
});

const emit = defineEmits(["select"]);

function isEven() {
  return props.number % 2 === 0;
}

function getClass() {
  return isEven() ? "border-red" : "border-green";
}

function onSelect() {
  emit("select", props.number);
}
</script>

<template>
  <div class="box" :class="getClass()">
    {{ number }}
    <button @click="onSelect" class="btn">Select</button>
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
  text-align: center;
}

.border-red {
  border-bottom: solid 8px red;
}

.border-green {
  border-bottom: solid 8px green;
}

.btn {
  display: block;
  margin-top: 20px;
}
</style>
