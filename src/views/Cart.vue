<template>
  <div class="pt-16">
    <h2 class="text-center text-2xl font-bold text-gray-600 p-4">My Cart</h2>
    <CartItemCard 
    v-for="getCartItem in getCartItems"
    :key="getCartItem.id"
    :cartItem="getCartItem"
    />
    <PaymentTotal />
  </div>
</template>

<script>
import CartItemCard from '../components/Cart/CartItemCard.vue'
import PaymentTotal from '../components/Cart/PaymentTotal.vue'

export default {
  components: {
    CartItemCard,
    PaymentTotal
  },
  computed: {
    getCartItems() {
      return this.$store.getters.cartItems
    }
  }
}
</script>
