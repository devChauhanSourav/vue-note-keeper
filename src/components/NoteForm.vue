<template>
  <form @submit.prevent="submitNote" class="flex flex-col gap-4 mb-6">
    <input
      v-model="title"
      type="text"
      placeholder="Note title"
      class="border border-gray-300 p-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-400"
    />
    <textarea
      v-model="content"
      placeholder="Note content..."
      class="border border-gray-300 p-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-400"
      rows="3"
    ></textarea>
    <button
      type="submit"
      class="bg-indigo-600 text-white py-2 rounded-lg hover:bg-indigo-700 transition"
    >
      Add Note
    </button>
  </form>
</template>


<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add-note'])

const title = ref('')
const content = ref('')

function submitNote() {
  const newNote = {
    title: title.value,
    content: content.value,
    pinned: false,
    createdAt: new Date().toISOString(),
  }

  emit('add-note', newNote)

  title.value = ''
  content.value = ''
}
</script>
