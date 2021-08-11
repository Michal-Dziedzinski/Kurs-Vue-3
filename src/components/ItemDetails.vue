<template>
  <section v-if="item">
    <h2>Basic information:</h2>
    <p>Name: {{ item.name }}</p>
    <p>Birth year: {{ item.birth_year }}</p>
    <p>Height: {{ item.height }}</p>
    <p>Mass: {{ item.mass }}</p>
  </section>
  <section v-else>
    <h2>OOOPS!</h2>
    <p>
      For some reason the resource yau are looking for does not exist or is
      unavailable, please, try someting else.
    </p>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'ItemDetails',
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  async setup(props) {
    const item = ref(null);

    try {
      const response = await fetch(`https://swapi.dev/api/people/${props.id}`);

      if (response.status !== 200) {
        throw new Error('Response status is different than 200');
      }
      const parsedResponse = await response.json();

      item.value = parsedResponse;
    } catch (error) {
      console.log(error);
    }

    return {
      item,
    };
  },
};
</script>

<style lang="scss" scoped></style>
