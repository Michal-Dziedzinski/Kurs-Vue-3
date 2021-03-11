<template>
  <div class="container">
    <CompositionComponent component-name="Composition component" />
    <OptionsComponent component-name="Options component" />
  </div>
</template>

<script>
import CompositionComponent from "./CompositionComponent";
import OptionsComponent from "./OptionsComponent";
export default {
  name: "MyAwsomeComponent",
  components: {
    CompositionComponent,
    OptionsComponent,
  },
};
</script>

<style lang="scss">
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
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
