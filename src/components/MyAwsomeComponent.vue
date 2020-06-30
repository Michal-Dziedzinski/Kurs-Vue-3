<template>
  <div class="container">
    <div v-if="error" class="error">{{error}}</div>
    <Suspense v-else>
      <template #default>
        <StarshipsList></StarshipsList>
      </template>
      <template #fallback>
        <AppLoader />
      </template>
    </Suspense>
  </div>
</template>

<script>
import { ref, onErrorCaptured } from "vue";
import StarshipsList from "./StarshipsList";
import AppLoader from "./AppLoader";

export default {
  name: "MyAwsomeComponent",
  components: {
    StarshipsList,
    AppLoader
  },
  setup() {
    const error = ref(null);

    onErrorCaptured(e => {
      error.value = e;
      return true;
    });

    return { error };
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
  background-color: #000;
  color: #fcd711;
}

.error {
  color: #cd3727;
}
</style>
