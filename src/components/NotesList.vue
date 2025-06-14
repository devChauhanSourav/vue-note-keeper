<template>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
    <div
      v-for="(note, index) in notes"
      :key="index"
      class="bg-slate-100 border-l-4 p-4 rounded-xl shadow-md relative"
      :class="note.pinned ? 'border-yellow-400' : 'border-slate-300'"
    >
      <h2 class="text-lg font-semibold text-slate-800">{{ note.title }}</h2>
      <p class="text-slate-600 mt-1">{{ note.content }}</p>

      <div class="flex justify-end mt-4 gap-2">
        <button
          @click="$emit('pin-note', index)"
          class="text-yellow-500 hover:text-yellow-600 transition text-sm"
        >
          📌 {{ note.pinned ? 'Unpin' : 'Pin' }}
        </button>
        <button
          @click="$emit('delete-note', index)"
          class="text-red-500 hover:text-red-600 transition text-sm"
        >
          ❌ Delete
        </button>
      </div>
    </div>
  </div>
</template>


<script setup>
import NoteItem from './NoteItem.vue'

const props = defineProps({
  notes: Array,
})

const emit = defineEmits(['delete-note', 'pin-note'])
</script>
