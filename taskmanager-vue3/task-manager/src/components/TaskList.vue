<script setup>
import TaskItem from './TaskItem.vue'

const props = defineProps({
  tasks: { type: Array, required: true },
})

const emit = defineEmits(['toggle-done', 'remove-task'])
</script>

<template>
  <ul>
    <task-item
      v-for="task in tasks"
      :key="task.id"
      :task="task"
      @toggle-done="$emit('toggle-done', $event)"
      @remove-task="$emit('remove-task', $event)"
    ></task-item>
    <li v-if="tasks.length === 0" style="color:#666; padding:6px 0;">تسکی وجود ندارد </li>
  </ul>
</template>
