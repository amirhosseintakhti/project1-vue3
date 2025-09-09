<script setup>
import {ref} from 'vue'
import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';

const tasks = ref([])

const addTask = (taskText) => {
  tasks.value.push({
    id:Date.now(),
    text: taskText,
    done:false
  })
}

const ToggleDone = (id) => {
  const task = tasks.value.find(t => t.id === id)
  if(task) task.done = !task.done
}

const removeTask = (id) => {
  tasks.value = tasks.value.filter(t => t.id !==id)
}

// const sumEventNumbers = ()=>{
//   let sum = 0;

//   numbers.forEach(n => {
//     if(n % 2 == 0){
//       sum += n
//     }
//   })
//   return sum
// }

</script>

<template>
<div style="max-width: 600px; margin: auto;">
  <h1 style="text-align:center;">مدیریت تسک‌ها</h1>
  <task-form @add-task="addTask"></task-form>
  <task-list :tasks="tasks" @toggle-done="toggleDone" @remove-task="removeTask"></task-list>
</div>
</template>

<style scoped></style>
