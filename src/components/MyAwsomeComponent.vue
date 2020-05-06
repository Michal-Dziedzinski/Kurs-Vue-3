<template>
  <div>
    <p>
      You have
      <strong>{{shares}}</strong> shares and their value is
      <strong>{{sharesValue}}$</strong>, because share price is
      <strong>{{sharePrice}}$</strong>
    </p>
    <button @click="changeNumberOfShares(1)">Buy one share</button>
    <button @click="changeNumberOfShares(5)">Buy five shares</button>
    <button @click="changeNumberOfShares(-1)">Sell one share</button>
    <button @click="changeNumberOfShares(-5)">Sell five shares</button>
  </div>
</template>

<script>
import { ref, computed, watch } from "vue";

export default {
  name: "MyAwsomeComponent",
  setup() {
    const shares = ref(15);
    const sharePrice = ref(20);
    const sharesValue = computed(() => shares.value * sharePrice.value);

    function changeNumberOfShares(number) {
      if (shares.value + number >= 0) {
        shares.value += number;
      }
    }

    watch(shares, (shares, prevShers) => {
      shares > prevShers ? getPrice(1, 5) : getPrice(-5, -1);
    });

    function getPrice(min, max) {
      const priceDiff = Math.floor(Math.random() * (max - min) + min);
      if (sharePrice.value + priceDiff >= 0) {
        sharePrice.value += priceDiff;
      }
    }

    return { shares, sharePrice, sharesValue, changeNumberOfShares };
  }
};
</script>
