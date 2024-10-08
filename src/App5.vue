<script setup>
import { ref, reactive, computed } from 'vue'

const isActive = ref(true)
const hasError = ref(false)

const activeClass = ref('active')
const errorClass = ref('text-danger')

const activeColor = ref('red')
const fontSize = ref(30)

const classObject = reactive({
  active: true,
  'text-danger': false
})

const isActiveForExtendedClassObject = ref(true)
const error = ref(null)

const extendedClassObject = computed(() => ({
  active: isActiveForExtendedClassObject.value && !error.value,
  'text-danger': error.value && error.value.type === 'fatal'
}))
</script>

<template>
  <!-- It will render: <div class="static active"></div> -->
  <div class="static" :class="{ active: isActive, 'text-danger': hasError }">App 5 variant 1</div>
  <!-- It will render: <div class="active"></div> -->
  <div :class="classObject">App 5 variant 2</div>
  <!-- It will render: <div class="active"></div> -->
  <div :class="extendedClassObject">App 5 variant 3</div>

  <div :class="[isActive ? activeClass : '', errorClass]">App 5 variant 4</div>

  <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">App 5 variant 5</div>
</template>
