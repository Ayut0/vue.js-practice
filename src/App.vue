<script setup>
let msg = "Hello from App.vue";

const upperCase = () => {
  msg = msg.toUpperCase();
};
upperCase();
const link = 'https://google.com';

const isActive = true;
const isBlack = true;

// const error = 'error occurred';
const stock = 0
</script>

<template>
  <h1>Vue 3 Starter</h1>
  <p>{{ msg }}</p>
  <div>
    <a v-bind:href="link">Google</a>
    <!-- Shorthand ver of v-bind -->
    <a :href="link">Google</a>
  </div>
  <p class="underline" :class = "{active:isActive, back: isBlack}">How to set up v-bind</p>

  <!-- v-if condition -->
  <div>
    <!-- <p v-if="error">{{ error }}</p> -->
    <p v-if="stock > 5">We have a couple of stocks</p>
    <p v-else-if="stock === 0">Unfortunately, we are out of those</p>
    <p v-else>There is no error</p>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.active {
  color: red;
}

.underline {
  text-decoration: underline;
}

.back {
  background-color: black;
}
</style>
