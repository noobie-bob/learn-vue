<script setup lang="ts">
import { ref } from 'vue'
const msg = ref("Hello World")
</script>

<template>
  <h1>Uppercase :{{ msg.toLocaleUpperCase() }}</h1>
  <h1>Lowercase :{{ msg.toLowerCase() }}</h1>
  <h1>If-else-ternary: {{ msg ? msg : "Yo type something" }}</h1>
  <h1>OR check: {{ msg || "Yo type something" }}</h1>
  <input v-model="msg">
  <input v-model="msg" class="padding-2">
</template>

<style scoped>
.padding-2 {
  margin-left: 1rem;
}
</style>