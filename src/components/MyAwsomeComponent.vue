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
import CompositionAPI from './CompositionAPI'
import OptionsAPI from './OptionsAPI'
export default {
  name: 'MyAwsomeComponent',
  components: {
    CompositionAPI,
    OptionsAPI,
  },
}
</script>

<style lang="scss" scoped>
.container {
  width: 100vw;
  height: 100vh;
}
.button {
  cursor: pointer;
  background-color: transparent;
  color: #000;
  border: 3px solid #000;
  padding: 10px 20px;
  font-size: 24px;
  outline: none;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: background-color 0.1s ease-in, color 0.1s ease-in,
    border-color 0.1s ease-in;
  margin-top: 10px;
  &:hover {
    background-color: #000;
    color: #fff;
    border-color: #000;
  }
}
.result {
  margin-top: 100px;
}
</style>
