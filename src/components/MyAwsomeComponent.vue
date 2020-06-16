<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">increment</button>
    <MyAwsomeComponentChild v-if="count < 3" />
  </div>
</template>

<script>
import {
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  ref,
  onRenderTracked,
  onRenderTriggered,
} from 'vue';

import MyAwsomeComponentChild from './MyAwsomeComponentChild';

export default {
  name: 'MyAwsomeComponent',
  components: {
    MyAwsomeComponentChild,
  },
  setup() {
    const count = ref(0);
    function increment() {
      count.value++;
    }
    console.log('setup');

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });
    onMounted(() => {
      console.log('onMounted');
    });
    onBeforeUpdate(() => {
      console.log('onBeforeUpdate');
    });
    onUpdated(() => {
      console.log('onUpdated');
    });
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount');
    });
    onUnmounted(() => {
      console.log('onUnmounted');
    });

    // onActivated
    // onDeactivated

    // onErrorCaptured

    onRenderTracked((e) => {
      console.log('onRenderTracked', e);
    });
    onRenderTriggered((e) => {
      console.log('onRenderTriggered', e);
    });
    return { count, increment };
  },
};
</script>

<style lang="scss"></style>
