<template>
  <div class="col-12 col-md-6 col-lg-4">
    <div class="card">
      <img
        class="card-img-top"
        :src="getImgUrl(product.name)"
        alt="Card image cap"
      />
      <div class="card-body">
        <h4 class="card-title mb-4">
          {{ product.name }}
        </h4>
        <div class="row">
          <div class="col-md-4">
            <p class="btn btn-danger btn-block">$ {{ product.price.USD }} </p>
          </div>
          <div class="col-md-8 cart-panel ">
            <input type="number" class="col-8" v-model="quantity" />
            <button @click="addToCart(product)" class="btn btn-success btn-block">
              Add to cart
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Product',
  props: ['product'],
  data () {
    return {
      quantity: 0
    }
  },
  methods: {
    getImgUrl (name) {
      return require('../assets/img/' + name + '.jpg')
    },
    addToCart (product) {
      this.$emit('add-to-cart', product, this.quantity)
    }
  }
}
</script>
<style scoped>
    img {
        width:300px;
        height:250px;
    }
    .cart-panel {
      display:inline-flex
    }
</style>
