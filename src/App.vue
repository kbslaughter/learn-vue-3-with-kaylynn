<template>
  <h1>{{ message }}</h1>

  <button v-on:click="replaceText('v-on is fun!')">Replace text</button>
  <button @click="replaceText('v-on is fun!')">Replace text</button>
    // the @ is a shorthand for v-on:

  <hr>
  <p>An input field where the user can ONLY enter numbers:</p>
  <input type="text" @keydown="handleInput($event)" />

  <hr />
  <div style="width:100px; height:100px; background-color: aqua;" @contextmenu.prevent="console.log('show a custom context menu')"></div>

</template>

<script setup>
import { ref } from 'vue';

let message = ref('Hello v-on!');

function replaceText(msg) {
  message.value = msg;
}

function handleInput(event) {
  console.log(event);
  let keyCode = event.keyCode
  if (keyCode < 48 || keyCode > 57) {
    event.preventDefault(); //vanilla js
  }
}

</script>

<style scoped>
#mouseover {
  text-align: right;
  background-color: purple;
  width: 300px;
  height: 300px;
}
</style>