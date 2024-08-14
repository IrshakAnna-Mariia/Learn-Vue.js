<script setup lang="ts">
import { ref } from 'vue'

const title = ref('My first vue application')
const author = ref('Alex')
const age = ref(21)
</script>

<template>
  <div>{{ title }} - {{ author }} - {{ age }}</div>
  <br />
  <button @click="age++">Increase age</button>
  <button @click="age--">Decrease age</button>
  <p>Change title here:</p>
  <input v-model="title" placeholder="Type here" />
  <p>Change author here:</p>
  <input v-model="author" placeholder="Type here" />
</template>
