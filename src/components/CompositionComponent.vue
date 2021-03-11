<template>
  <div>
    <h1>{{ props.componentName }}</h1>
    <div>
      First value:
      {{ valueToIncrement }}
      Second value:
      {{ state.secondValueToIncrement }}
      <button @click="increment">Increment</button>
    </div>
    <div>
      First value:
      {{ valueToDecrement }}
      Second value:
      {{ state.secondValueToDecrement }}
      <button @click="decrement">Decrement</button>
    </div>
    <div class="box" :style="{ backgroundColor: activeColor }"></div>
  </div>
</template>

<script>
import { ref, computed, onMounted, watch, reactive } from "vue";

export default {
  name: "CompositionComponent",
  props: {
    componentName: {
      required: true,
      type: String,
    },
  },
  setup(props) {
    console.log("Hi, I am created from Vue 3");

    onMounted(console.log("Hi, I am mounted from Vue 3"));

    const state = reactive({
      secondValueToIncrement: 100,
      secondValueToDecrement: 110,
    });

    //Increment
    const valueToIncrement = ref(0);
    function increment() {
      valueToIncrement.value++;
      state.secondValueToIncrement++;
    }
    watch(valueToIncrement, () => {
      console.log(`Vue 3. Now value is ${valueToIncrement.value}`);
    });

    //Decrement
    const valueToDecrement = ref(10);
    function decrement() {
      valueToDecrement.value--;
      state.secondValueToDecrement--;
    }

    //Radnomize color
    function randomizeColor() {
      return Math.floor(Math.random() * 255);
    }
    const activeColor = computed(
      () => `rgb(${randomizeColor()},${randomizeColor()},${randomizeColor()})`
    );

    return {
      state,
      valueToIncrement,
      increment,
      valueToDecrement,
      decrement,
      activeColor,
      props,
    };
  },
};
</script>

<style scoped>
.box {
  width: 150px;
  height: 150px;
}
</style>
