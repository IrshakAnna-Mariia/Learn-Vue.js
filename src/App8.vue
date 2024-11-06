<script setup>
function say(message) {
  alert(message)
}
</script>

<template>
  <button @click="say('hello')">Say hello</button>
  <button @click="say('bye')">Say bye</button>

  <!-- the click event's propagation will be stopped -->
  <a @click.stop="doThis"></a>

  <!-- the submit event will no longer reload the page -->
  <form @submit.prevent="onSubmit"></form>

  <!-- modifiers can be chained -->
  <a @click.stop.prevent="doThat"></a>

  <!-- just the modifier -->
  <form @submit.prevent></form>

  <!-- only trigger handler if event.target is the element itself -->
  <!-- i.e. not from a child element -->
  <div @click.self="doThat">...</div>
</template>
