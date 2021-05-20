<template>
  <section class="wrapper">
    <div v-if="error" class="error">{{ error }}</div>
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
import { ref, onErrorCaptured } from 'vue'
import ItemDetails from '@/components/ItemDetails.vue'
import BaseLoader from '@/components/BaseLoader'

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
    const error = ref(null)

    onErrorCaptured((e) => {
      error.value = e
    })

    return { error }
  },
}
</script>

<style lang="scss" scoped>
.wrapper {
  max-width: 1024px;
  margin-left: auto;
  margin-right: auto;
  position: relative;
  min-height: 100vh;
}
</style>
