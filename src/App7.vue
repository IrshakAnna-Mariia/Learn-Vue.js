<script setup>
import { ref, reactive } from 'vue'

const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
const todos = ref([
  { name: 'TODO 1', isComplete: false },
  { name: 'TODO 2', isComplete: true },
  { name: 'TODO 3', isComplete: false }
])

const parentMessage = ref('Parent')

const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})
</script>

<template>
  <!-- v-for -->
  <li v-for="item in items" :key="item.message">
    {{ item.message }}
  </li>

  <li v-for="(item, index) in items" :key="item.message">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>

  <!-- v-for with an Object -->
  <ul>
    <li v-for="value in myObject" :key="value">
      {{ value }}
    </li>
  </ul>

  <li v-for="(value, key) in myObject" :key="key">{{ key }}: {{ value }}</li>

  <li v-for="(value, key, index) in myObject" :key="key">{{ index }}. {{ key }}: {{ value }}</li>

  <!-- v-for with a Range -->
  <span v-for="n in 10" :key="n">{{ n }}</span>

  <!-- v-for with v-if -->
  <template v-for="todo in todos" :key="todo.name">
    <li v-if="!todo.isComplete">
      {{ todo.name }}
    </li>
  </template>
</template>
