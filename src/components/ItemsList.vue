<template>
  <section v-if="items" class="list">
    <router-link
      v-for="(item, index) in items"
      :key="index"
      :to="{ name: 'ItemPage', params: { id: index + 1 } }"
      class="list__item"
    >
      <SingleItem :item="item" />
    </router-link>
  </section>
</template>

<script>
import { ref } from 'vue'
import SingleItem from '@/components/SingleItem'

export default {
  name: 'ItemsList',
  components: {
    SingleItem,
  },
  async setup() {
    const items = ref(null)
    const response = await fetch('https://swapi.dev/api/people')
    const parsedResponse = await response.json()

    items.value = [...parsedResponse.results]

    return {
      items,
    }
  },
}
</script>

<style lang="scss" scoped>
.list {
  display: grid;
  grid-gap: 25px;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  justify-items: center;
  align-items: center;
  &__item {
    text-decoration: none;
    width: 100%;
  }
}
</style>
