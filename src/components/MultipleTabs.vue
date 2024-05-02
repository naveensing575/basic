<template>
  <div class="tab">
    <button
      @click="active = 'HomeTab'"
      :class="{ active: active === 'HomeTab' }"
    >
      Home
    </button>
    <button
      @click="active = 'AboutTab'"
      :class="{ active: active === 'AboutTab' }"
    >
      About
    </button>
    <button
      @click="active = 'JobsTab'"
      :class="{ active: active === 'JobsTab' }"
    >
      Jobs
    </button>

    <keep-alive>
      <component :is="active" />
    </keep-alive>
  </div>
</template>

<script>
import HomeTab from "./Tabs/HomeTab.vue";
import AboutTab from "./Tabs/AboutTab.vue";
import JobsTab from "./Tabs/JobsTab.vue";

export default {
  name: "MultipleTabs",
  components: {
    HomeTab,
    AboutTab,
    JobsTab,
  },
  data() {
    return {
      active: "HomeTab",
    };
  },
};
</script>

<style scoped>
.tab {
  margin-top: 50px;
}

.tab button {
  padding: 10px 20px;
  margin-right: 10px;
  border: none;
  background-color: #ccc;
  color: #333;
  cursor: pointer;
}

.tab button.active {
  background-color: #007bff;
  color: #fff;
}
</style>
