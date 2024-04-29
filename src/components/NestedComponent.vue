<template>
  <div>
    <h1>Nested Component</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="js">
export default {
  name: "NestedComponent",
  inject: ["message"],
};
</script>

<style lang="css"></style>
