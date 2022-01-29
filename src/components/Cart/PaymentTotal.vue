<template>
<div class="flex justify-center mb-4">
  <div class="w-full md:w-1/2 text-center shadow-2xl bg-green-500 rounded-md pb-4">
    <h2 class="text-xl capitalize p-4 text-white">Total amount: <span class="font-bold">${{ cart_total.toFixed(2) }}</span></h2>
    <button @click="aler('sorry this is under construction build')" class="text-white shadow  px-2 py-2 rounded bg-blue-500">Pay with Paypal</button>
  </div>
</div>
</template>

<script>
export default {
  computed: {
    cart_total() {
      return this.$store.getters.cartTotal
    }
  },
  methods: {
    aler(message) {
      alert(message)
    }
  }
}
</script>