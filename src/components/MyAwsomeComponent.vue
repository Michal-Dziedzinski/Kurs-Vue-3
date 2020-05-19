<template>
  <div>
    <div>
      <p>Masks: {{ masks }}</p>
      <p v-if="masks > 3">You can buy a mask!</p>
      <p v-else-if="masks > 0 && masks <= 3">
        You can buy a mask, but hurry up!
      </p>
      <p v-else>You can't buy a mask, it's out of stock!</p>
      <button
        class="btn"
        @click="buyMask"
        :disabled="!masks"
        :class="{ 'btn--warning': masks > 0 && masks <= 3 }"
      >
        Buy a mask
      </button>
    </div>
    <div>
      <img
        :src="images[currentImage]"
        :alt="`Image ${currentImage + 1}`"
        class="image"
      />
      <button
        class="btn"
        @click="changeImage"
        :disabled="currentImage >= images.length - 1"
      >
        Change Image
      </button>
    </div>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue';

export default {
  name: 'MyAwsomeComponent',
  setup() {
    const masks = ref(5);

    const styles = reactive({
      btn: {
        backgroundColor: '#17a2b8',
        color: '#fff',
      },
    });

    function buyMask() {
      masks.value--;
    }

    const images = ref([
      'https://dziedziuch.samurajprogramowania.pl/projects/1-slider/images/1.jpg',
      'https://dziedziuch.samurajprogramowania.pl/projects/1-slider/images/2.jpg',
      'https://dziedziuch.samurajprogramowania.pl/projects/1-slider/images/3.jpg',
      'https://dziedziuch.samurajprogramowania.pl/projects/1-slider/images/4.jpg',
      'https://dziedziuch.samurajprogramowania.pl/projects/1-slider/images/5.jpg',
    ]);

    const currentImage = ref(0);

    function changeImage() {
      currentImage.value++;
    }

    return {
      masks,
      buyMask,
      ...toRefs(styles),
      images,
      currentImage,
      changeImage,
    };
  },
};
</script>

<style lang="scss">
.btn {
  color: #fff;
  background-color: #369b6d;
  border: none;
  padding: 5px 10px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.1 ease-in;
  &--warning {
    background-color: #ffc107;
    color: #000;
  }
  &:disabled {
    cursor: default;
    background-color: #bd2130;
  }
}
.image {
  margin-top: 50px;
  width: 300px;
  display: block;
}
</style>
