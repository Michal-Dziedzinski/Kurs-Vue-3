<template>
  <button class="button" @click="addItem">Add to cart</button>
</template>

<script>
export default {
  name: 'AddToCartButton',
  // emits: ['add-item-to-cart'],
  // emits: { 'add-item-to-cart': (qty) => typeof qty === 'number' },
  // emits: {
  //   'add-item-to-cart': ({ name, qty }) => {
  //     if (typeof qty === 'number' && typeof name === 'string') {
  //       return true;
  //     } else {
  //       console.warn('siema, źle żęś podał payload');
  //       return false;
  //     }
  //   },
  // },
  emits: {
    'add-item-to-cart': ({ name, qty }) =>
      typeof qty === 'number' && typeof name === 'string',
  },
  setup(props, { emit }) {
    function addItem() {
      // emit('add-item-to-cart');
      // emit('add-item-to-cart', 3);
      emit('add-item-to-cart', { name: 'product', qty: '2' });
    }
    return { addItem };
  },
};
</script>

<style lang="scss" scoped>
.button {
  cursor: pointer;
  background-color: transparent;
  color: #000;
  border: 3px solid #000;
  padding: 10px 20px;
  font-size: 24px;
  outline: none;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: background-color 0.1s ease-in, color 0.1s ease-in,
    border-color 0.1s ease-in;
  margin-top: 10px;
  &:hover {
    background-color: #000;
    color: #fff;
    border-color: #000;
  }
}
</style>
