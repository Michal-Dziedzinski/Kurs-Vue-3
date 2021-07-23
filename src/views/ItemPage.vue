<template>
  <section>
    <div v-if="error">{{ error }}</div>
    <Suspense v-else>
      <template #default>
        <ItemDetails :id="id" />
      </template>
      <template #fallback>
        <BaseLoader />
      </template>
    </Suspense>
  </section>
</template>

<script>
import { ref, onErrorCaptured } from 'vue';
import ItemDetails from '@/components/ItemDetails.vue';
import BaseLoader from '@/components/BaseLoader';

export default {
  name: 'ItemPage',
  components: {
    ItemDetails,
    BaseLoader,
  },
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  setup() {
    const error = ref(null);

    onErrorCaptured((e) => {
      error.value = e;
    });

    return { error };
  },
};
</script>
