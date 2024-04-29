<template>
  <form class="form" @submit.prevent="onSubmit">
    <h3>User Input Form</h3>
    <label for="name">Name:</label>
    <input
      type="text"
      id="name"
      v-model.trim.lazy="formValues.name"
      placeholder="Name"
    /><br />
    <label for="email">Email:</label>
    <input type="text" v-model="formValues.email" placeholder="Email" />
    <div>
      <h4>Two-way binding</h4>
      <p>{{ formValues }}</p>
    </div>
    <div>
      <h3>Select country</h3>
      <select id="country" v-model="formValues.country">
        <option value="India">India</option>
        <option value="USA">USA</option>
        <option value="UK">UK</option>
      </select>
    </div>
    <div>
      <h3>Select job location</h3>
      <select id="jobLocation" multiple v-model="formValues.jobLocation">
        <option value="India">India</option>
        <option value="USA">USA</option>
        <option value="UK">UK</option>
        <option value="Dubai">Dubai</option>
        <option value="Australia">Australia</option>
      </select>
    </div>
    <div></div>
    <h3>Remote Work?</h3>
    <input
      type="checkbox"
      id="remoteWork"
      true-value="true"
      false-value="false"
      v-model="formValues.remoteWork"
    /><label for="remoteWork">Open to remote work</label>
    <div></div>
    <h3>Select skillSet</h3>
    <div>
      <input
        type="checkbox"
        id="html"
        value="html"
        v-model="formValues.skillSet"
      />
      <label for="html">HTML</label>
    </div>
    <div>
      <input
        type="checkbox"
        id="css"
        value="css"
        v-model="formValues.skillSet"
      />
      <label for="css">CSS</label>
    </div>
    <div>
      <input type="checkbox" id="js" value="js" v-model="formValues.skillSet" />
      <label for="js">JS</label>
    </div>
    <div>
      <h3>Years of Experience</h3>
      <input
        type="radio"
        id="0-2"
        value="0-2"
        v-model="formValues.yearsOfExp"
      />
      <label for="0-2">0-2</label>
      <input
        type="radio"
        id="3-5"
        value="3-5"
        v-model="formValues.yearsOfExp"
      />
      <label for="3-5">3-5</label>
      <input
        type="radio"
        id="6-10"
        value="6-10"
        v-model="formValues.yearsOfExp"
        @keyup.enter="onSubmit"
      />
      <label for="6-10">6-10</label>
    </div>
    <button type="submit" class="btn">Submit</button>
  </form>
  <NestedComponent />
</template>

<script lang="js">
import NestedComponent from './NestedComponent.vue';

export default {
  app: "UserForm",
  components: {
    NestedComponent,
  },
  provide: {
      message: "Hello, this is a nested component(managed using provide/inject)",
    },
  data() {
    return {
      formValues: {
        name: "",
        email: "",
        country: "",
        jobLocation: [],
        remoteWork: false,
        skillSet: [],
        yearsOfExp: 0,
      },
    };
  },

  methods: {
    onSubmit() {
      if (
        !this.formValues.name ||
        !this.formValues.email ||
        !this.formValues.country ||
        this.formValues.jobLocation.length === 0 ||
        this.formValues.skillSet.length === 0 ||
        !this.formValues.yearsOfExp
      ) {
        return alert("Please fill all the required fields");
      } else {
        console.log("Thank you for your registration", this.formValues);
        return this.formValues;
      }
    },
  },
};
</script>

<style scoped>
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
.btn {
  padding: 5px 10px;
  font-size: large;
  margin-top: 20px;
  border-radius: 5px;
  border: none;
  cursor: pointer;
  color: black;
  background: #1df0ff;
}
</style>
