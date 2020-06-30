<template>
  <section v-if="ships">
    <h1>Ships list:</h1>
    <StarshipItem v-for="(ship, index) in ships" :key="index" :ship="ship" />
  </section>
</template>

<script>
import { ref } from "vue";
import StarshipItem from "./StarshipItem";

export default {
  name: "StarshipList",
  components: {
    StarshipItem
  },
  async setup() {
    const ships = ref(null);

    const response = await fetch("https://swapi.dev/api/starships/");
    const parsedResponse = await response.json();

    ships.value = [...parsedResponse.results];

    return {
      ships
    };
  }
};
</script>

<style lang="scss" scoped>
</style>