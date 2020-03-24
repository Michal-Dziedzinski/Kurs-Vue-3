<template>
  <div>
    <button @click="sayHello">Say hello</button>
  </div>
</template>

<script>
export default {
  name: "MyAwsomeComponent",
  setup() {
    function sayHello() {
      const welcomeText = "Siema, co tam?";
      console.log(addExclamationMark(welcomeText));
    }

    function addExclamationMark(text) {
      return `${text}!`;
    }
    return { sayHello };
  }
};
</script>
