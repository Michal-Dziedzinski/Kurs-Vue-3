<template>
  <article class="item">
    <p class="item__text">{{ item.name }}</p>
  </article>
</template>

<script>
export default {
  name: 'SingleItem',
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.item {
  color: #fff;
  padding: 15px 0;
  border: 1px solid #fcd711;
  text-align: center;
  transition: background-color 0.1s ease-in, color 0.1s ease-in;
  font-weight: 700;
  &:hover {
    background-color: #fcd711;
    color: #000;
  }
  &__text {
    margin: 0;
  }
}
</style>
