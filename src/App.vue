<template>
  <div id="app">
    <siemaApp />
    <MyAwsomeComponent />
  </div>
</template>

<script>
import MyAwsomeComponent from './components/MyAwsomeComponent.vue';
import siemaApp from './components/siemaApp';

export default {
  name: 'App',
  components: {
    MyAwsomeComponent,
    siemaApp,
  },
};
</script>
