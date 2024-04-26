<template>
  <template v-for="user in users.user" :key="user.id">
    <p>Name: {{ user.name }}</p>
    <p>Age: {{ user.age }}</p>
    <p v-show="user.hobbies">Hobbies: {{ user.hobbies }}</p>
    <h4>Total number of users: {{ totalUsers }}</h4>
  </template>
</template>

<script>
export default {
  name: "UserList",
  data() {
    return {
      users: {
        user: [
          {
            name: "Naveen",
            age: 23,
            hobbies: ["Football", "Singing", "playing guitar"],
          },
          {
            name: "Jasnoor",
            age: 24,
          },
        ],
      },
    };
  },
  computed: {
    totalUsers() {
      return this.users.user.length;
    },
  },
};
</script>
