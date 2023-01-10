<script setup>
import { ref } from 'vue'
import { useTodoListStore } from '../stores/todoList.js'

// eslint-disable-next-line no-undef
const todo = ref('')
const store = useTodoListStore()

function addItemAndClear(item) {
  if (item.length === 0) {
    return
  }
  store.addTodo(item)
  todo.value = ''
}
</script>

<template>
  <div class="relative w-full rounded-md border border-gray-300 px-3 py-2 shadow-sm focus-within:border-blue-600 focus-within:ring-1 focus-within:ring-blue-600">
    <label for="name" class="absolute -top-2 left-2 -mt-px inline-block bg-white px-1 text-xs font-medium text-gray-900">Todo</label>
    <input v-model="todo" type="text" name="name" id="name" class="block w-full border-0 p-0 text-gray-900 placeholder-gray-500 focus:ring-0 sm:text-sm" placeholder="À Faire...">
    
  </div>
  <button
    @click="addItemAndClear(todo)"
    type="button"
    class="mt-6 inline-flex items-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-sm font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
  >
    Add
  </button>
</template>

<style scoped>
</style>