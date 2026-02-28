<script setup lang="ts">
import { ref } from 'vue'
const header = ref('Shopping List App')
const items = ref([
  { id: 1, data: 'item 1' },
  { id: 2, data: 'item 4' },
  { id: 3, data: 'item 3' },
  { id: 4, data: 'item 2' },
])
const items2 = ref({
  'id-1': { id: 1, data: 'item 1' },
  'id-3': { id: 2, data: 'item 4' },
  'id-4': { id: 3, data: 'item 3' },
  'id-2': { id: 4, data: 'item 2' },
})
</script>

<template>
  <h1>{{ header }}</h1>
  <h3>Item list1</h3>
  <ul>
    <li v-for="{ id, data } in items" :key="id">{{ data }}</li>
  </ul>
  <h3>Item list2</h3>
  <ul>
    <li v-for="({ id, data }, idx) in items2" :key="id">{{ idx }}: {{ data }}</li>
  </ul>
</template>

<style scoped>
.padding-2 {
  margin-left: 1rem;
}
</style>
