<script setup lang="ts">
import { ref } from 'vue'
const header = ref('Shopping List App')
const items = ref(['item 1', 'item 4', 'item 3', 'item 2'])
const reorderItems = () => {
  items.value.sort()
}
const resetItems = () => {
  items.value = ['item 1', 'item 4', 'item 3', 'item 2']
}
const addItem = (item: string) => {
  items.value.push(item)
}
</script>

<template>
  <h1>{{ header }}</h1>
  <ul>
    <li v-for="(item, index) in items" :key="index">
      <input v-model="item" />
    </li>
  </ul>
  <input type="text" placeholder="Add an item" @keyup.enter="
      if ($event.target) {
    addItem(($event.target as HTMLInputElement).value)
      ; ($event.target as HTMLInputElement).value = ''
  }
    " />
  <button class="padding-2" @click="reorderItems">Reorder Items</button>
  <button class="padding-2" @click="resetItems">Reset Items</button>
</template>

<style scoped>
.padding-2 {
  margin-left: 1rem;
}
</style>
