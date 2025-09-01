<script setup>
import {ref} from 'vue'

const tasks = ref([
  {id:1, title:'تمرین یوگا', done:false},
  {id:2, title:'خوردن غذای سالم', done:false},
  { id: 3, title: 'خواندن ۱۰ صفحه کتاب 📖', done: false }
])
</script>

<template>
  <div>
    <h2>لیست کارها</h2>
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <input type="checkbox" v-model="task.done">
        <span :style="{textDecoration: task.done ? 'line-through' : 'none'}">{{ task.title}}</span>
      </li>
    </ul>
  </div>
</template>