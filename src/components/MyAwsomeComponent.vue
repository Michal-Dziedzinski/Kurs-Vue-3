<template>
  <!-- <div>
    <h1>Price: {{state.price}}$</h1>
    <button @click="makeOrder">Make next order</button>
    <p>Quantity: {{state.quantity}}</p>
    <p>Order total price: {{state.totalPrice}}</p>
    <p>Tax: {{state.tax}}</p>
  </div>-->
  <div>
    <h1>Price: {{price}}$</h1>
    <button @click="makeOrder">Make next order</button>
    <p>Quantity: {{quantity}}</p>
    <p>Order total price: {{totalPrice}}</p>
    <p>Tax: {{tax}}</p>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";

export default {
  name: "MyAwsomeComponent",
  setup() {
    const state = reactive({
      quantity: 0,
      price: 100,
      totalPrice: 0,
      tax: 0
    });

    function makeOrder() {
      state.quantity++;
      state.totalPrice = state.quantity * state.price;
      state.tax = state.totalPrice * 0.23;
    }

    return { makeOrder, ...toRefs(state) };
  }
};
</script>
