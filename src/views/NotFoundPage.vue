<template>
  <section class="not-found-page">
    <h2 class="not-found-page__header">OOOPS!</h2>
    <p>This page does not exist. Try something else, my padawan.</p>
  </section>
</template>

<script>
export default {
  name: 'NotFoundPage',
};
</script>

<style lang="scss" scoped>
.not-found-page {
  text-align: center;

  &__header {
    color: #fcd711;
  }
}
</style>
