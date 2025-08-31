<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <div>
    <button
      @click="count++"
      style="padding: 10px 14px; border-radius: 8px; cursor: pointer"
    >{{ count }}</button>
  </div>
</template>

<style scoped>
button {
  border: 1px solid #ddd;
  background: #fef3c7;
}
</style>
