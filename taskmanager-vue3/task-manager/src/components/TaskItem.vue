<script setup>
const props = defineProps({
  task:{type:Object , required :true}
})

const emit = defineEmits(['toggle-done', 'remove-task'])

const toggle = () => emit('toggle-done' , props.task.id)
const remove = () => emit('remove-task' , props.task.id)

</script>

<template>
  <li style="display: flex; align-items: center; gap: 10px; padding: 6px 0;">
    <input type="checkbox" :checked="task.done" @change="toggle">
    <span :style="{ textDecoration: task.done ? 'line-through' : 'none', flex:1 }">
      {{ task.text }}
    </span>
    <button @click="remove" style="cursor:pointer;">حذف</button>
  </li>
</template>