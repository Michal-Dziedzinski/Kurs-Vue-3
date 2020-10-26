<template>
  <div class="container">
    <button class="button" 
    @click="changeEventName" 
    @mousedown="changeEventName"
    @mouseup="changeEventName"
    @dblclick="changeEventName"
    @mousemove="changeEventName"
    @mouseover="changeEventName"
    @mousewheel="changeEventName"
    @mouseout="changeEventName">
      siema
    </button>
    <ul>
      <li></li>
    </ul>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "MyAwsomeComponent",
  setup() {
    const eventName = ref('');
    const eventArray = ref([])

    function changeEventName(e) {
      eventName.value = e.type;
    } 

    return { eventName, changeEventName };
  }
};
</script>

<style lang="scss">
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
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
  &:hover {
    background-color: #000;
    color: #fff;
    border-color: #000;
  }
}
</style>
