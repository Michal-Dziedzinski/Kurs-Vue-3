<template>
  <div class="container">
    <h1 class="header">Api comparision</h1>
    <div class="components">
      <CompositionAPI component-name="Composition component" />
      <OptionsAPI component-name="Options component" />
    </div>
  </div>
</template>

<script>
import CompositionAPI from './CompositionAPI';
import OptionsAPI from './OptionsAPI';
export default {
  name: 'MyAwsomeComponent',
  components: {
    CompositionAPI,
    OptionsAPI,
  },
};
</script>

<style lang="scss" scoped>
.container {
  width: 100vw;
  height: 100vh;
  margin: 20px;
}
.header {
  margin-bottom: 20px;
}
</style>
