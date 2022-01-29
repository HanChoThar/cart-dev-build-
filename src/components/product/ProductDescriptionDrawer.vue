<template>
  <div class="w-2/3  md:w-1/4 shadow-2xl h-screen fixed left-0 top-0 bg-white">
    <div v-if="product" class="p-4 rounded-md text-gray-600">
      <div class="flex justify-between mb-10">
        <h2 class="font-bold text-xl">{{ product.name }}</h2>
        <button @click="$emit('close', false)">X</button>
      </div>
      <p>{{ product.description }}</p>
      <h3 class="text-center py-4 font-bold">${{ product.price.toFixed(2) }}</h3>
      <div v-if="product_total" class="text-center pb-3">
        <h2>In Cart</h2>
        <h4>{{ product_total }}</h4>
      </div>

      <div class="flex justify-center">
        <button @click="addToCart" class="p-2 bg-gray-800 text-white rounded mr-2">Add</button>
        <button @click="removeFromCart" class="p-2 bg-gray-800 text-white rounded">Remove</button>
      </div>
    </div>
    </div>
</template>

<script>
export default {
  props: ['product'],
  methods: {
    addToCart() {
      this.$store.commit('addToCart', this.product)
    },
    removeFromCart() {
      this.$store.commit('removeFromCart', this.product)
    }
  },
  computed: {
    product_total() {
      return this.$store.getters.cart(this.product)
    }
  }

}
</script>