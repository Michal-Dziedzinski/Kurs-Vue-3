<template>
  <div class="container">
    <AwsomeButton :text="'hello'">
      <div class="squere"></div>
    </AwsomeButton>
    <!-- <AwsomeButton :text="'hello'">
      <template #image>
        <img src="../assets/logo.png" alt="logo" class="image" />
      </template>
      <template #text>
        <h1>tratata</h1>
      </template>
    </AwsomeButton>-->
  </div>
</template>

<script>
import AwsomeButton from "./AwsomeButton";

export default {
  name: "MyAwsomeComponent",
  components: {
    AwsomeButton
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
.image {
  width: 20px;
  height: 20px;
}

.squere {
  width: 50px;
  height: 50px;
  background-color: red;
}
</style>
