<template>
  <div>
    <h1>{{ componentName }}</h1>
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
export default {
  name: "OptionsComponent",
  props: {
    componentName: {
      required: true,
      type: String,
    },
  },
  data() {
    return {
      valueToIncrement: 0,
      valueToDecrement: 10,
      state: {
        secondValueToIncrement: 100,
        secondValueToDecrement: 110,
      },
    };
  },
  computed: {
    activeColor() {
      return `rgb(${this.randomizeColor()},${this.randomizeColor()},${this.randomizeColor()})`;
    },
  },
  watch: {
    valueToIncrement() {
      console.log(`Vue 2. Now value is ${this.valueToIncrement}`);
    },
  },
  created() {
    console.log("Hi, I am created from Vue 2");
  },
  mounted() {
    console.log("Hi, I am mounted from Vue 2");
  },
  methods: {
    increment() {
      this.valueToIncrement++;
      this.state.secondValueToIncrement++;
    },
    decrement() {
      this.valueToDecrement--;
      this.state.secondValueToDecrement--;
    },
    randomizeColor() {
      return Math.floor(Math.random() * 255);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  width: 150px;
  height: 150px;
}
</style>
