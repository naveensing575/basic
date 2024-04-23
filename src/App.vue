<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1 v-if="msg">{{ msg }}</h1>
  <h1 v-else>Hey this is my first vue app</h1>
  <p v-text="name"></p>
  <p v-html="name"></p>
  <button v-bind="{ disabled: binding }" @click="msg = 'Hello World'">
    Click Me
  </button>
  <p v-bind="{ class: classBinding }">Class Binding</p>
  <button @click="classBinding = 'expired'">Expired</button>
  <button @click="classBinding = 'success'">Success</button>
  <button @click="binding = !binding">Toggle Binding</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      msg: "Welcome to Vue.js App",
      name: "<i>Naveen Singh</i>",
      binding: false,
      classBinding: "underline",
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
.underline {
  text-decoration: underline;
}
.overline {
  text-decoration: overline;
}
.expired {
  color: red;
}
.success {
  color: green;
}
</style>
