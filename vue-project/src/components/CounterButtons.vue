<script setup lang="ts">
const emit = defineEmits(['increment', 'reset'])
</script>

<template>
  <div class="counter-buttons">
    <button @click="emit('increment')">Incrementar</button>
    <button @click="emit('reset')">Reset</button>
  </div>
</template>

<style scoped>
button { margin-right: 0.5rem; }
</style>
