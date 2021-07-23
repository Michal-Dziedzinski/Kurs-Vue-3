<template>
  <section>
    <div v-if="error">{{ error }}</div>
    <Suspense v-else>
      <template #default>
        <ItemsList />
      </template>
      <template #fallback>
        <BaseLoader />
      </template>
    </Suspense>
  </section>
</template>

<script>
import { ref, onErrorCaptured } from 'vue';
import BaseLoader from '@/components/BaseLoader';
import ItemsList from '@/components/ItemsList';

export default {
  name: 'HomePage',
  components: {
    BaseLoader,
    ItemsList,
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
