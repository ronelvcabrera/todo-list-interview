<template>
  <q-page class="row items-center justify-evenly">
      <TodoForm @submit="addTodo"/>
      <div>
        {{ todos }}
      </div>
  </q-page>
</template>

<script setup>
import TodoForm from '../components/TodoForm.vue'
import { ref } from 'vue'

const todos = ref([])


function addTodo(props) {
  todos.value.push(props)
}


</script>
