<template>
  <ItemsList :items="candidates" />
</template>

<script>
import { ref, computed } from 'vue';
import ItemsList from './items/ItemsList';

export default {
  name: 'MyAwsomeComponent',
  components: {
    ItemsList,
  },
  setup() {
    const candidatesWithParty = computed(() =>
      candidates.value.filter(({ party }) => party),
    );
    const candidates = ref([
      {
        id: 1,
        firstName: 'Robert',
        lastName: 'Biedroń',
        age: 44,
        party: 'Wiosna Roberta Biedronia',
        opinionPool: 4,
      },
      {
        id: 2,
        firstName: 'Krzysztof',
        lastName: 'Bosak',
        age: '37',
        party: 'Konfederacja Wolność i Niepodległość',
        opinionPool: 7,
      },
      {
        id: 3,
        firstName: 'Andrzej',
        lastName: 'Duda',
        age: 47,
        party: null,
        opinionPool: 49,
      },
      {
        id: 4,
        firstName: 'Szymon',
        lastName: 'Hołownia',
        age: 43,
        party: null,
        opinionPool: 22,
      },
      {
        id: 5,
        firstName: 'Marek',
        lastName: 'Jakubiak',
        age: 61,
        party: 'Federacja dla Rzeczypospolitej',
        opinionPool: null,
      },
      {
        id: 6,
        firstName: 'Małgorzata',
        lastName: 'Kidawa-Błońska',
        age: 63,
        party: 'Platforma Obywatelska',
        opinionPool: 5,
      },
      {
        id: 7,
        firstName: 'Władysław',
        lastName: 'Kosiniak-Kamysz',
        age: 38,
        party: 'Polskie Stronnictwo Ludowe',
        opinionPool: 12,
      },
      {
        id: 8,
        firstName: 'Mirosław',
        lastName: 'Piotrowski',
        age: 64,
        party: 'Ruch Prawdziwa Europa',
        opinionPool: null,
      },
      {
        id: 9,
        firstName: 'Paweł',
        lastName: 'Tanajno',
        age: 44,
        party: null,
        opinionPool: 1,
      },
      {
        id: 10,
        firstName: 'Stanisław',
        lastName: 'Żółtek',
        age: 64,
        party: 'Kongres Nowej Prawicy',
        opinionPool: null,
      },
    ]);

    return { candidates, candidatesWithParty };
  },
};
</script>

<style lang="scss">
.siema {
  background-color: red;
}
</style>
