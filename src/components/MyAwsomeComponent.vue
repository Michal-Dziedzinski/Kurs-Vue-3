<template>
  <div>
    <h1>Price: {{price}}$</h1>
    <button @click="makeOrder">Make next order</button>
    <p>Quantity: {{quantity}}</p>
    <p>Order total price: {{totalPrice}}</p>
    <p>Tax: {{tax}}</p>
  </div>
</template>

<script>
import { computed, toRefs, reactive } from "vue";

export default {
  name: "MyAwsomeComponent",
  setup() {
    const state = reactive({
      quantity: 0,
      price: 100,
      totalPrice: computed(() => state.price * state.quantity),
      tax: computed(() => state.totalPrice * 0.23)
    });

    function makeOrder() {
      state.quantity++;
    }

    return { makeOrder, ...toRefs(state) };
  }
};
</script>
