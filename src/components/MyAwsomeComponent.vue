<template>
  <div class="container">
    <BaseInput name="siema" v-model="inputText" />
    <p>{{ inputText }}</p>
    <button v-show="inputText" class="button" @click="revertText">
      Revert text
    </button>
  </div>
</template>

<script>
import { ref } from 'vue';
import BaseInput from './BaseInput';

export default {
  name: 'MyAwsomeComponent',
  components: {
    BaseInput,
  },
  setup() {
    const inputText = ref('');

    function revertText() {
      return (inputText.value = inputText.value
        .split('')
        .reverse()
        .join(''));
    }

    return { inputText, revertText };
  },
};
</script>

<style lang="scss">
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  flex-direction: column;
}
.input {
  margin-top: 10px;
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
.outer {
  width: 100px;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #42b883;
  margin-top: 10px;
}
.inner {
  width: 50px;
  height: 50px;
  background-color: #35495e;
}
.form {
  display: flex;
  flex-direction: column;
}
</style>
