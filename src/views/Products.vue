<template>
  <div class="container mb-5">
    <div class="row">
      <div class="col">
        <div class="row">
          <Product
            v-for="(product, i) in inventory"
            :key="i"
            :product="product"
            @add-to-cart="addToCart"
          />
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
  methods: {
    addToCart (product, quantity) {
      this.cart = JSON.parse(localStorage.getItem('cart')) ?? {}
      console.log(this.cart)
      if (this.cart[product.name]) {
        this.cart[product.name].quantity += quantity
        localStorage.setItem('cart', JSON.stringify(this.cart))
        return
      }
      this.cart[product.name] = product
      this.cart[product.name].quantity = quantity
      localStorage.setItem('cart', JSON.stringify(this.cart))
    }
  },
  components: {
    Product
  }
}
</script>
