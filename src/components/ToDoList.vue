<script setup>
import { useTodoListStore } from '../stores/todoList.js'
import { storeToRefs } from 'pinia'
const store = useTodoListStore()
const { todoList } = storeToRefs(store)
const { toggleCompleted, deleteTodo } = store
</script>

<template>
  <ul
    role="list"
    class="mt-8 w-full space-y-3"
  >
    <li
      v-for="todo in todoList"
      :key="todo.id"
      class="flex justify-between overflow-hidden rounded-md bg-white px-6 py-4 shadow"
    >
      <!-- Your content -->
      <span :class="{ 'text-green-500 line-through': todo.completed }">{{ todo.item }}</span>
      <div>
        <span @click.stop="toggleCompleted(todo.id)" class="cursor-pointer px-4">&#10004;</span>
        <span @click="deleteTodo(todo.id)" class="cursor-pointer">&#10060;</span>
      </div>
    </li>
  </ul>
</template>

<style scoped>
</style>