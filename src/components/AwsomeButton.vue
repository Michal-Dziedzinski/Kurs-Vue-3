  
<template>
  <button class="button">{{text}}</button>
</template>

<script>
export default {
  name: "AwsomeButton",
  props: {
    text: {
      type: String,
      default: "siema"
    }
  }
};
</script>

<style lang="scss" scoped>
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
  &:hover {
    background-color: #000;
    color: #fff;
    border-color: #000;
  }
}
</style>