<script>
import AppButton from "./components/AppButton.vue";
import AppInput from "./components/AppInput.vue";

export default {
  components: { AppButton, AppInput },
  data() {
    return {
      username: {
        value: "",
        valid: false,
      },
      password: {
        value: "",
        valid: false,
      },
    };
  },
  computed: {
    valid() {
      return this.username.valid && this.password.valid;
    },
  },
  methods: {
    submit() {
      console.log("submit");
    },
    update({ name, value, valid }) {
      this[name] = {
        value,
        valid,
      };
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <form @submit.prevent="submit">
      <AppInput
        name="username"
        required
        :min="4"
        type="text"
        :value="username.value"
        @update="update"
      />

      <AppInput
        name="password"
        required
        :min="6"
        type="password"
        :value="password.value"
        @update="update"
      />
      <AppButton
        text="Click"
        background="slateblue"
        color="white"
        :disabled="!valid"
      />
    </form>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
  margin-top: 200px;
}
form {
  max-width: 400px;
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
