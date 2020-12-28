<template>
  <div id="app">
    <MyAwsomeComponent />
  </div>
</template>

<script>
import MyAwsomeComponent from './components/MyAwsomeComponent.vue';

export default {
  name: 'App',
  components: {
    MyAwsomeComponent,
  },
};
</script>

<style lang="scss">
*,
*::after,
*::before {
  font-family: Arial, Helvetica, sans-serif;
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
