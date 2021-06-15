<template>
  <div class="cart-item-cart">
    <h3>cartTotal:${{ cart_total.toFixed(2) }}</h3>

    <button class="view-product-button">pay by credit card</button>
  </div>
</template>
<script>
export default {
  props: ['product'],

  computed: {
    cart_total() {
      return this.$store.getters.cartTotal;
    },
  },
};
</script>