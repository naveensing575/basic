<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1 v-if="msg">{{ msg }}</h1>
  <h1 v-else>Hey this is my first vue app</h1>
  <p v-text="name"></p>
  <p v-html="name"></p>
  <button v-bind="{ disabled: binding }" v-on:click="msg = 'Hello World'">
    Click Me
  </button>
  <p v-bind="{ class: classBinding }">Class Binding</p>
  <button @click="classBinding = 'expired'">Expired</button>
  <button @click="classBinding = 'success'">Success</button>
  <button @click="binding = !binding">Toggle Binding</button>
  <p v-for="item in car" :key="item">{{ item }}</p>
  <h1>Count: {{ count }}</h1>
  <button v-on:click="increment">Increment Count</button>
  <button v-on:click="decrement">Decrement Count</button>
  <h2>Volume Tracker</h2>
  <h3>Volume: {{ volume }}</h3>
  <div>
    <button @click="volume++">+</button>
    <button @click="volume--">-</button>
  </div>
  <UserForm />
  <!-- <UserList /> -->
</template>

<script>
import UserForm from "./components/UserForm.vue";
// import UserList from "./components/UserList.vue";
export default {
  name: "App",
  components: {
    UserForm,
    // UserList,
  },
  data() {
    return {
      msg: "Welcome to Vue.js App",
      volume: 0,
      name: "<i>Naveen Singh</i>",
      binding: false,
      classBinding: "underline",
      car: ["BMW", "Mercedes", "Audi"],
      count: 0,
    };
  },
  methods: {
    increment() {
      return this.count + 1;
    },
    decrement() {
      return this.count - 1;
    },
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("Listening to high volume is not advisable");
      }
    },
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
