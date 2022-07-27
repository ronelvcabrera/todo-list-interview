<template>
  <q-page class="cols items-center justify-evenly">
      <TodoForm todo="props.todo" @submit="addTodo"/>
       <q-list bordered separator>
          <q-item clickable v-ripple v-for="(todo,idx) in todos">
            <q-item-section>{{ todo }}</q-item-section>

            <q-item-section top side>
              <div class="text-grey-8 q-gutter-xs">
                <q-btn class="gt-xs" size="12px" flat dense round icon="edit" />
                <q-btn @click="deleteTodo(idx)" class="gt-xs" size="12px" flat dense round icon="delete" />
              </div>
            </q-item-section>
          </q-item>
        </q-list>
  </q-page>
</template>

<script setup>
import TodoForm from '../components/TodoForm.vue'
import { ref } from 'vue'

const todos = ref([])
const props = defineProps(['todo'])

function addTodo(props) {
  todos.value.push(props)
}

function deleteTodo(idx) {
  todos.value.splice(idx,1)
}




</script>
