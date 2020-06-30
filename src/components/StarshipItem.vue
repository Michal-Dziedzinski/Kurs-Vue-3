<template>
  <p class="ship">{{ship.name}}</p>
</template>

<script>
export default {
  name: "StarshipItem",
  props: {
    ship: {
      type: Object,
      default: () => {}
    }
  }
};
</script>

<style lang="scss" scoped>
.ship {
  color: #fff;
}
</style>
