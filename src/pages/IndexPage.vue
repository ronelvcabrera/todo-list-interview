<template>
  <q-page class="cols items-center justify-evenly">
      <TodoForm @submit="addTodo"/>
       <q-list bordered separator>
          <q-item clickable v-ripple v-for="todo in todos">
            <q-item-section>{{ todo }}</q-item-section>
          </q-item>
        </q-list>
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
