<template>
  <h1>Popup</h1>
  <input type="text" v-model="name" />
  <button @click="$emit('close', name)">Click Me</button>
</template>

<script>
export default {
  name: "PopupModal",
  emits: {
    close: (name) => {
      if (!name) {
        return false;
      } else {
        console.log(name);
        return true;
      }
    },
  },
  data() {
    return {
      name: "",
    };
  },
};
</script>
