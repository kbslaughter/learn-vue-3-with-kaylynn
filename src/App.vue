<template>
  <div class="card">
    <h2>Message: {{ message }}</h2>
    <h2>Number: {{ number }}</h2>

    <button @click="changeMessageToUpperCase">
      Change message to upper case
    </button>

    <button @click="incrementNumber">Increment number</button>
  </div>
</template>

<script setup>
import ref from 'vue'
let message = ref('Hello, Reactivity!')
let number = ref(1)

function changeMessageToUpperCase() {
  message = message.toUpperCase()
  console.log(message)
}

function incrementNumber() {
  number += 1
  console.log(number)
}
</script>

<style scoped>
.card {
  background-color: purple;
  color: white;
  padding: 20px 10px;
  margin-bottom: 10px;
}

</style>