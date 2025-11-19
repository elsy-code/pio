<script setup lang="ts">
import CounterButtons from './CounterButtons.vue'

const props = defineProps<{ count?: number }>()
const emit = defineEmits<{ (e: 'increment'): void; (e: 'reset'): void }>()
defineSlots<{ info?: () => unknown }>()
</script>

<template>
  <div class="counter-controls">
    <p>Cuenta pasada como prop: <strong>{{ props.count }}</strong></p>
    <CounterButtons @increment="emit('increment')" @reset="emit('reset')" />
    <slot name="info" />
  </div>
</template>

<style scoped>
.counter-controls { border-top: 1px dashed #ddd; padding-top: 0.75rem;
 margin-top: 0.75rem; }
 button{margin-right: 0,5rem, }
</style>
