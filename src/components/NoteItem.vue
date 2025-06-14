<template>
  <div
    class="border p-3 rounded mb-2 shadow-sm"
    :class="{ 'bg-yellow-100': note.pinned }"
  >
    <div class="flex justify-between">
      <h3 class="font-bold">{{ note.title }}</h3>
      <div class="space-x-2">
        <button @click="$emit('pin-note')" class="text-yellow-600">📌</button>
        <button @click="$emit('delete-note')" class="text-red-500">🗑️</button>
      </div>
    </div>
    <p class="mt-1">{{ note.content }}</p>
    <p class="text-xs text-gray-400 mt-1">{{ formattedDate }}</p>
  </div>
</template>

<script setup>
import { computed } from 'vue'
const props = defineProps({
  note: Object,
})

const formattedDate = computed(() =>
  new Date(props.note.createdAt).toLocaleString()
)
</script>
