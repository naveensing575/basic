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
  <template v-for="user in users.user" :key="user.id">
    <p>Name: {{ user.name }}</p>
    <p>Age: {{ user.age }}</p>
    <p v-show="user.hobbies">Hobbies: {{ user.hobbies }}</p>
  </template>
  <h1>Count: {{ count }}</h1>
  <button v-on:click="increment">Increment Count</button>
  <button v-on:click="decrement">Decrement Count</button>
  <div class="form">
    <h3>User Input Form</h3>
    <label for="name">Name:</label>
    <input type="text" v-model="formValues.name" placeholder="Name" /><br />
    <label for="email">Email:</label>
    <input type="text" v-model="formValues.email" placeholder="Email" />
    <div>
      <h4>Two-way binding</h4>
      <p>{{ formValues }}</p>
    </div>
  </div>
  <div>
    <h3>Select country</h3>
    <select id="country" v-model="formValues.country">
      <option value="India">India</option>
      <option value="USA">USA</option>
      <option value="UK">UK</option>
    </select>
  </div>
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
      car: ["BMW", "Mercedes", "Audi"],
      formValues: {
        name: "",
        email: "",
        country: "",
      },
      count: 0,
      users: {
        user: [
          {
            name: "Naveen",
            age: 23,
            hobbies: ["Football", "Singing", "playing guitar"],
          },
          {
            name: "Jusnoor",
            age: 24,
          },
        ],
      },
    };
  },
  methods: {
    increment() {
      return (this.count += 1);
    },
    decrement() {
      return (this.count -= 1);
    },
  },
};
</script>

<style>
body {
  background: #2c3e50;
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 20px;
}
label {
  margin: 10px;
}
input {
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  margin-bottom: 10px;
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
