<template>
  <div class="home pt-14 ">
    <ProductDescriptionDrawer 
    v-show="showProductDrawer"
    :product="product"
    @close="close($event)"
    />
    <ProdcutSummaryCard
    v-for="product in products"
    :key="product.id"
    :product="product"
    @viewProduct="viewProduct($event)"
     />
  </div>
</template>

<script>
import data from '../../data/data.json'
import ProdcutSummaryCard from '../components/product/ProductSummaryCard.vue'
import ProductDescriptionDrawer from '../components/product/ProductDescriptionDrawer.vue'

export default {
  name: 'Home',
  components: {
    ProdcutSummaryCard,
    ProductDescriptionDrawer
  },
  data() {
    return {
      products: data.products,
      product: null,
      showProductDrawer: false
    }
  },
  methods: {
    viewProduct(product) {
      this.product = product
      this.showProductDrawer = true
      console.log(product)
    },
    close(damn) {
      this.showProductDrawer = damn
    }
  },
  mounted(){
    console.log(this.products)
  }
}
</script>
