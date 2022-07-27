<template>
   <div class="q-pa-md">
    <div class="q-gutter-md" style="max-width: 300px">
      <q-input v-model="text" label="Add To Dos" />
    </div>
    <q-btn @click="addTodo" color="primary" label="Add Todo" />
    <q-btn @click="clearText" color="negative" label="Clear" />

  </div>
</template>

<script setup>
import { ref } from 'vue'
import { defineEmits } from 'vue'

const text = ref("")
const emit = defineEmits(['submit'])

function addTodo() {
    if(text.value) {
        emit('submit', text.value)
        text.value = ""
    }
}

function clearText() {
  text.value = ""
}
</script>