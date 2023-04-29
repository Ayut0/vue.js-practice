<script setup>
let msg = "Hello from App.vue";

const upperCase = () => {
  msg = msg.toUpperCase();
};
upperCase();
const link = "https://google.com";

const isActive = true;
const isBlack = true;

// const error = 'error occurred';
const stock = 0;

const languages = ["TypeScript", "JavaScript", "Vue.js"];

const users = [
  { id: 1, name: "John", email: "john@test.com", admin: true },
  { id: 2, name: "Mike", email: "mike@test.com", admin: false },
  { id: 3, name: "Kevin", email: "kevin@test.com", admin: false },
];

const user = {
  id: 1,
  name: "James",
  email: "james@test,com",
  admin: true,
};
</script>

<template>
  <h1>Vue 3 Starter</h1>
  <p>{{ msg }}</p>
  <div>
    <a v-bind:href="link">Google</a>
    <!-- Shorthand ver of v-bind -->
    <a :href="link">Google</a>
  </div>
  <p class="underline" :class="{ active: isActive, back: isBlack }">
    How to set up v-bind
  </p>

  <!-- v-if condition -->
  <div>
    <!-- <p v-if="error">{{ error }}</p> -->
    <p v-if="stock > 5">We have a couple of stocks</p>
    <p v-else-if="stock === 0">Unfortunately, we are out of those</p>
    <p v-else>There is no error</p>
  </div>

  <!-- array -->
  <h2>Array</h2>
  <p>{{ languages[0] }}</p>
  <p>{{ languages[1] }}</p>
  <p>{{ languages[2] }}</p>
  <!-- v-for loop -->
  <div>
    <ul>
      <li v-for="(language, index) in languages" :key="index">
        {{ language }}
      </li>
    </ul>
  </div>

  <!-- object -->
  <h2>Object</h2>
  <p v-for="user in users" :key="user">
    {{ user.id }}:{{ user.name }}:{{ user.email }}
  </p>
  <h3>Unordered list</h3>
  <ul>
    <li v-for="user in users" :key="user.id">
      {{ user.id }}:{{ user.name }}:{{ user.email }}
    </li>
  </ul>
  <h3>Properties in order</h3>
  <div v-for="(value, name) in user" :key="value">{{ name }}:{{ value }}</div>

  <!-- To show the index of the array, use the second argument of the v-for -->
  <h3>v-for:array and V-for:object</h3>
  <div v-for="user in users" :key="user.id">
    <div v-for="(value, name) in user" :key="value">
      {{ name }}:{{ value }}
    </div>
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
