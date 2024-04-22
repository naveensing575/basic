<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1 v-if="msg">{{ msg }}</h1>
  <h1 v-else>Hey this is my first vue app</h1>
  <p v-text="name"></p>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      msg: "Welcome to Vue.js App",
      name: "Naveen Singh",
    };
  },
};
</script>

<style>
body {
  background: #2c3e50;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
</style>
