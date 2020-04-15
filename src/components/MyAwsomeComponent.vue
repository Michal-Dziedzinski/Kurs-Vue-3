<template>
  <div>
    <button @click="incrementPension">Increment my pension</button>
    <p>Your pension will be: {{pension}}</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "MyAwsomeComponent",
  setup() {
    const pension = ref(100);

    console.log(pension);

    function incrementPension() {
      pension.value++;
    }

    return { pension, incrementPension };
  }
};
</script>
