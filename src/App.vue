<template>
  <div id="app">
    <MyAwesomeComponent />
  </div>
</template>

<script>
import MyAwesomeComponent from "./components/MyAwesomeComponent.vue";
export default {
  name: "App",
  components: {
    MyAwesomeComponent,
  },
};
</script>

<style lang="scss">
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
