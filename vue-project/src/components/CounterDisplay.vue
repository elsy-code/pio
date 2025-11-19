<script setup lang="ts">
import { computed } from 'vue'
import { useCounterStore } from '../stores/counter'

const props = defineProps<{ showDouble?: boolean }>()
const store = useCounterStore()
const count = computed(() => store.count)
const doubleCount = computed(() => store.doubleCount)
</script>

<template>
  <div class="counter-display">
    <p>Cuenta (desde store): <strong>{{ count }}</strong></p>
    <p v-if="props.showDouble">Cuenta doble: <strong>{{ doubleCount }}</strong></p>
  </div>
</template>

<style scoped>
.counter-display { margin-bottom: 0.75rem; }
</style>
