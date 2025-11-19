<script setup lang="ts">
import { computed } from 'vue'
import { useCounterStore } from './stores/counter'
import CounterButtons from './components/CounterButtons.vue'
import CounterControls from './components/CounterControls.vue'

const counter = useCounterStore()
const count = computed(() => counter.count)
const doubleCount = computed(() => counter.doubleCount)

function reset() {
  counter.count = 0
}

function increment() {
  counter.increment()
}
</script>

<template>
  <div class="app">
    <h1>Ejemplo: Pinia + Componentes en Vue 3 (componentes separados)</h1>

    <!-- 2) Componente que emite eventos al padre -->
    <section>
      <h2>CounterButtons (emite eventos)</h2>
      <CounterButtons @increment="increment" @reset="reset" />
    </section>



    
    <section>
      <h3>Estado (solo lectura)</h3>
      <p>Cuenta: <strong>{{ count }}</strong></p>
      <p>Cuenta doble (computed): <strong>{{ doubleCount }}</strong></p>
    </section>
  </div>
</template>

<style scoped>
.app { max-width: 700px; margin: 2rem auto; font-family: system-ui, sans-serif; }
section { margin-bottom: 1rem; padding: 0.5rem 0; }
button { margin-right: 0.5rem; }
</style>
