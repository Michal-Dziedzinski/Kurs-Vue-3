<template>
  <div id="app">
    <MyAwsomeComponent />
  </div>
</template>

<script>
import MyAwsomeComponent from "./components/MyAwsomeComponent.vue";

export default {
  name: "App",
  components: {
    MyAwsomeComponent
  }
};
</script>

<style lang="scss">
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
}
</style>
