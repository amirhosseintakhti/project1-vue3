<script setup>
import {ref} from 'vue'

const newTask = ref('')

const emit = defineEmits(['add-task'])

const handleSubmit = () => {
  if(newTask.value.trim() === '')return
  emit('add-task' , newTask.value)
  newTask.value = ''
}

</script>

<template>
  <form @submit.prevent="handleSubmit" class="task-form">
    <input type="text" v-model="newTask" placeholder="تسک جدید وارد کن..."/>
    <button type="submit">افزودن</button>
  </form>
</template>

<style scoped>
.task-form {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
}
.task-form input {
  flex: 1;
  padding: 6px;
}
</style>
