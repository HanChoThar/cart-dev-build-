<template>
  <div class="flex justify-center ">
    <div class="bg-gray-200 text-gray-600 shadow w-full md:w-1/2 text-center rounded-md mb-2 mt-4 py-4">
      <h2 class="font-bold pb-4"> {{ product.name }}</h2>
      <div>Price: <span class="font-bold">{{ product.price.toFixed(2) }}</span> </div>
      <p>Description: {{ description }}</p>
      <div>{{ product.catergory }}</div>
      <button @click="$emit('viewProduct', product)" class="bg-gray-800 text-white rounded p-2 mt-3">View</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      required: true
    }
  },
  computed: {
    description() {
      return this.product.description.substring(0, 100)
    }
  }
}
</script>