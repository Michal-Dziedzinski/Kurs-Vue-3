<template>
  <div class="search">
    <!-- <input :name="name" :type="type" class="input" :placeholder="placeholder" /> -->
    <input
      :name="name"
      :type="type"
      class="input"
      placeholder="First name"
      :value="firstName"
      @input="(e) => $emit('update:firstName', e.target.value)"
      v-model="text"
    />
    <input
      :name="name"
      :type="type"
      class="input"
      placeholder="Last name"
      :value="lastName"
      @input="(e) => $emit('update:lastName', e.target.value)"
      v-model="text"
    />
    <!-- <input
      :name="name"
      :type="type"
      class="input"
      :placeholder="placeholder"
      :value="modelValue"
      @input="(e) => $emit('update:modelValue', e.target.value)"
      v-model="text"
    /> -->
    <!-- <input
      :name="name"
      :type="type"
      class="input"
      :placeholder="placeholder"
      v-model="text"
    /> -->
    <!-- <input
      :name="name"
      :type="type"
      class="input"
      :placeholder="placeholder"
      @input="text = $event.target.value"
      :value="text"
    /> -->
    <label :for="name" class="label">{{ placeholder }}</label>
  </div>
  <!-- <p class="result">{{ text }}</p> -->
  <!-- <button v-show="text" class="button" @click="revertText">Revert text</button> -->
</template>

<script>
// import { ref } from 'vue';
export default {
  name: 'BaseInput',
  props: {
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      default: 'text',
    },
    placeholder: {
      type: String,
      default: 'Type something...',
    },
    firstName: {
      type: String,
    },
    lastName: {
      type: String,
    },
  },
  // setup() {
  //   const text = ref('');

  //   function revertText() {
  //     return (text.value = text.value
  //       .split('')
  //       .reverse()
  //       .join(''));
  //   }

  //   return { text, revertText };
  // },
};
</script>

<style lang="scss" scoped>
.search {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.input {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  width: 300px;
  border-bottom: 3px solid #35495e;
  &:focus {
    outline: none;
    border-bottom-color: #42b883;
  }
  &::-webkit-input-placeholder {
    color: #000;
  }
  &:placeholder-shown + .label {
    opacity: 0;
    visibility: hidden;
    transform: translateY(-40px);
  }
}
.label {
  font-size: 16px;
  margin-left: 20px;
  margin-top: 5px;
  display: block;
  transition: opacity 0.3s, visibility 0.3s, transform 0.3s;
}
.result {
  margin-top: 100px;
}
.button {
  margin-top: 100px;
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
