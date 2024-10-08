<script setup>
import { reactive, ref } from 'vue'

// variables with refs (string, number or boolean allowed):
const count = ref(0)

async function increment() {
  count.value++
  await nextTick()
  // Now the DOM is updated because of nextTick()
}

// variables with reactive:
const state = reactive({ count: 0 })

async function incrementState() {
  state.count++
}

// object with ref:
const obj = ref({
  nested: { count: 0 },
  arr: ['foo', 'bar']
})

function mutateDeeply() {
  // these will work as expected.
  obj.value.nested.count++
  obj.value.arr.push('baz')
}

// object with reactive:
const raw = {}
const proxy = reactive(raw)

proxy !== raw
reactive(raw) === proxy
reactive(proxy) === proxy
</script>

<template>
  <button @click="increment">
    {{ count }}
  </button>
  <button @click="incrementState">
    {{ state.count }}
  </button>
</template>
