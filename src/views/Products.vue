<template>
  <div class="container mb-5">
    <div class="row">
      <div class="col">
        <div class="row">
          <Product v-for="(product, i) in inventory" :key="i" :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import food from '../food.json'
import Product from '../components/Product.vue'
export default {
  name: 'Products',
  data () {
    return {
      inventory: food,
      cart: {}
    }
  },
  components: {
    Product
  }
}
</script>
