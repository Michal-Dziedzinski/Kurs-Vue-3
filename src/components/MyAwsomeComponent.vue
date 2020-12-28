<template>
  <div class="container">
    <BaseInput
      name="input"
      v-model:firstName="firstName"
      v-model:lastName="lastName"
    />
    <p class="result">{{ firstName }}</p>
    <p class="result">{{ lastName }}</p>
    <button class="button" @click="revertText">Revert text</button>
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
    const text = ref('');
    const firstName = ref('');
    const lastName = ref('');

    function revertText() {
      firstName.value = firstName.value
        .split('')
        .reverse()
        .join('');
      lastName.value = lastName.value
        .split('')
        .reverse()
        .join('');
    }

    return { text, firstName, lastName, revertText };
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
