<template>
  <section>
    <Suspense>
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
};
</script>
