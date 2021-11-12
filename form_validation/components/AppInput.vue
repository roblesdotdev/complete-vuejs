<script setup>
import { computed } from "vue";
const props = defineProps({
  name: String,
  required: Boolean,
  type: String,
  min: Number,
  value: String,
});

const emit = defineEmits(["update"]);

const error = computed(() => validate(props.value));

function capitalize(name) {
  return name.toLowerCase().replace(/\w/, (first) => first.toUpperCase());
}

function input($event) {
  const val = $event.target.value;

  emit("update", {
    name: props.name,
    value: val,
    valid: !validate(val),
  });
}

function validate(value) {
  if (props.required && props.value.length === 0) {
    return "This value is required.";
  }
  if (props.min && value.length < props.min) {
    return `The minimum length ${props.min}`;
  }
}
</script>

<template>
  <div class="input-wrapper">
    <div class="label">
      <label :for="name">{{ capitalize(name) }}</label>
      <div class="error">{{ error }}</div>
    </div>
    <input :type="type" :id="name" :value="value" @input="input" />
  </div>
</template>

<style scoped>
.input-wrapper {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.error {
  color: red;
}

.label {
  display: flex;
  justify-content: space-between;
}

input {
  box-sizing: border-box;
  background: none;
  color: black;
  border: 1px solid silver;
  border-radius: 5px;
  margin: 2px;
  font-size: 16px;
  padding: 10px;
  width: 100%;
}
</style>
