<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-100 to-slate-200 p-6">
    <div class="max-w-3xl mx-auto bg-white shadow-xl rounded-2xl p-6">
      <h1 class="text-4xl font-bold text-center text-indigo-600 mb-6">📝 Note Keeper</h1>
      <NoteForm @add-note="addNote" />
      <NotesList
        :notes="notes"
        @delete-note="deleteNote"
        @pin-note="pinNote"
      />
    </div>
  </div>
</template>


<script setup>
import { ref, onMounted, watch } from 'vue'
import NoteForm from './components/NoteForm.vue'
import NotesList from './components/NotesList.vue'

const notes = ref([])

function addNote(note) {
  notes.value.unshift(note)
}

function deleteNote(index) {
  notes.value.splice(index, 1)
}

function pinNote(index) {
  notes.value[index].pinned = !notes.value[index].pinned
}

// Load from localStorage on startup
onMounted(() => {
  const savedNotes = localStorage.getItem('notes')
  if (savedNotes) {
    notes.value = JSON.parse(savedNotes)
  }
})

// Save to localStorage when notes change
watch(notes, (newNotes) => {
  localStorage.setItem('notes', JSON.stringify(newNotes))
}, { deep: true })
</script>
