<template>
<div class="flex justify-center">
  <div class="w-full md:w-1/2 p-4 bg-gray-200 mb-2 rounded-md text-gray-600 text-center">
      <div class="flex justify-between mb-4">
        <h3><span class="font-bold">Product Name: </span>{{ cartItem.name }}</h3>
        <h4><span class="font-bold">In Cart: </span>{{ cartItem.quantity }}</h4>
        <h4><span class="font-bold">Total Cost: </span>{{ totalCost.toFixed(2) }}</h4>
      </div>
      <p>{{ description }}</p>
  </div>
</div>
</template>

<script>
export default {
  props: {
    cartItem: {
      type: Object,
      required: true
    }
  },
  computed: {
    description() {
      return this.cartItem.description.substring(0, 100)
    },
    totalCost() {
      return this.cartItem.quantity * this.cartItem.price
    }
  }
}
</script>