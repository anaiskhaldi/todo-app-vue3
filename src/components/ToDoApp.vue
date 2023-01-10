<script setup>
import ToDoForm from './ToDoForm.vue'
import ToDoList from './ToDoList.vue'

</script>

<template>
  <div class="min-h-screen flex items-center justify-center">
    <!-- We've used 3xl here, but feel free to try other max-widths based on your needs -->
    <div class="min-w-500 flex flex-col items-center justify-center bg-white p-8">
      <h1 class="text-xl font-bold mb-6">To Do List</h1>
      <ToDoForm />
      <ToDoList />
    </div>
  </div>
</template>

<style scoped>
</style>