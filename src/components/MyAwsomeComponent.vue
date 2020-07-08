<template>
  <div class="container">
    <AwsomeButton text="Log in" @click="isModalVisible = true" />
    <teleport to="#modal">
      <AwsomeModal v-show="isModalVisible" />
    </teleport>
    <AwsomeFooter />
  </div>
</template>

<script>
import { ref } from "vue";
import AwsomeButton from "./AwsomeButton";
import AwsomeFooter from "./AwsomeFooter";
import AwsomeModal from "./AwsomeModal";

export default {
  name: "MyAwsomeComponent",
  components: {
    AwsomeButton,
    AwsomeFooter,
    AwsomeModal
  },
  setup() {
    const isModalVisible = ref(false);

    return { isModalVisible };
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
</style>
