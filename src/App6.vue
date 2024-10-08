<script setup>
import { ref } from 'vue'

const awesome = ref(true)
const type = ref('C')
const ok = ref(true)
</script>

<template>
  <!-- v-if -->
  <div>
    <h1 v-if="awesome">Vue is awesome!</h1>
  </div>

  <!-- v-else -->
  <div>
    <button @click="awesome = !awesome">Toggle</button>

    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>
  </div>

  <!-- v-else-if -->
  <div>
    <div v-if="type === 'A'">A</div>
    <div v-else-if="type === 'B'">B</div>
    <div v-else-if="type === 'C'">C</div>
    <div v-else>Not A/B/C</div>
  </div>

  <!-- v-if on <template> -->
  <template v-if="ok">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
  </template>

  <!-- v-show: the element is always rendered regardless of initial condition, with CSS-based toggling -->
  <div>
    <h1 v-show="ok">Hello!</h1>
  </div>
</template>
