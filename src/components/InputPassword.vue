<script setup>
import { ref, computed } from 'vue';

const isPasswordVisible = ref(false);

const inputType = computed(() => {
  return isPasswordVisible.value ? "text" : "password";
});

const buttonText = computed(() => {
  return isPasswordVisible.value ? "Hide Password" : "Show Password";
});

function showPassword() {
  isPasswordVisible.value = !isPasswordVisible.value;
}
</script>

<template>
  <div class="container text-center input-password">
    <h1 class="my-3">Exercise Input Password</h1>
    <input :type="inputType" name="" id="password" class="form-control">
    <div class="d-block">
      <span id="show-password" class="mt-2 btn btn-primary" @click="showPassword()">
        {{ buttonText }}
      </span>
    </div>
  </div>
</template>

<style scoped>
.input-password {
  max-width: 500px;
  margin: 0 auto;
}
</style>
