<template>
  <div>
    <p>Hi, I'm Child component</p>
    <p>Window size: Width: {{ width }}, Height: {{ height }}</p>
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
} from 'vue';

export default {
  name: 'MyAwsomeComponentChild',
  setup() {
    console.log('child setup');
    const width = ref(0);
    const height = ref(0);

    function changeWindowSize() {
      width.value = window.innerWidth;
      height.value = window.innerHeight;
    }

    onBeforeMount(() => {
      console.log('child onBeforeMount');
    });
    onMounted(() => {
      console.log('child onMounted');
      window.addEventListener('resize', changeWindowSize);
    });
    onBeforeUpdate(() => {
      console.log('child onBeforeUpdate');
    });
    onUpdated(() => {
      console.log('child onUpdated');
    });
    onBeforeUnmount(() => {
      console.log('child onBeforeUnmount');
      window.removeEventListener('resize', changeWindowSize);
    });
    onUnmounted(() => {
      console.log('child onUnmounted');
    });

    return { height, width };
  },
};
</script>

<style lang="scss" scoped></style>
