<template>
  <div>
    <h1>Your Cart</h1>
    <div v-if="cartIsEmpty">
      <p>You currently don't have any items in your shopping cart!</p>
    </div>
    <div v-else>
      <CartList :products="cart" />
    </div>
  </div>
</template>

<script>
import CartList from "../components/CartList.vue";
export default {
  name: "CartView",
  components: {
    CartList,
  },
  data() {
    return {};
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    },
    cartIsEmpty() {
      if (this.$root.$data.cart.length === 0) {
        return true;
      } else {
        return false;
      }
    },
  },
  methods: {},
};
</script>
