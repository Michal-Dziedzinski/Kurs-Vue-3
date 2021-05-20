<template>
  <section v-if="item">
    <h2>Basic information:</h2>
    <p>Name: {{ item.name }}</p>
    <p>Birth year: {{ item.birth_year }}</p>
    <p>Height: {{ item.height }}</p>
    <p>Mass: {{ item.mass }}</p>
  </section>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'ItemDetails',
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  async setup(props) {
    const item = ref(null)
    const response = await fetch(`https://swapi.dev/api/people/${props.id}`)
    const parsedResponse = await response.json()

    item.value = parsedResponse

    return {
      item,
    }
  },
}
</script>

<style lang="scss" scoped></style>
