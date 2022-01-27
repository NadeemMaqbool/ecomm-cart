<template>
  <section class="jumbotron text-center">
    <div class="container">
      <h1 class="jumbotron-heading">E-COMMERCE CART</h1>
    </div>
  </section>

  <div class="container mb-4">
    <div class="row">
      <div class="col-12">
        <div class="table-responsive">
          <table class="table table-striped">
            <thead>
              <tr>
                <th scope="col"></th>
                <th scope="col">Product</th>
                <th scope="col" class="text-center">Quantity</th>
                <th scope="col" class="text-right">Price</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, i) in cart" :key='i'>
                <td></td>
                <td>{{ item.name }}</td>
                <td>{{ item.quantity }}</td>
                <td class="text-right">{{ (item.price.USD * item.quantity).toFixed(2) }}</td>
                <td class="text-right">
                  <button @click="removeItem(item.name)" class="btn btn-sm btn-danger">
                    <font-awesome-icon icon="trash" />
                  </button>
                </td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td><strong>Total</strong></td>
                <td class="text-right"><strong>{{ getTotalAmount() }} €</strong></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      cart: {}
    }
  },
  methods: {
    getTotalAmount () {
      return Object.values(this.cart)
        .reduce((acc, item) => acc + (item.quantity * item.price.USD), 0)
        .toFixed(2)
    },
    removeItem (itemName) {
      delete this.cart[itemName]
      localStorage.setItem('cart', JSON.stringify(this.cart))
    }
  },
  beforeMount () {
    this.cart = JSON.parse(localStorage.getItem('cart'))
  }
}
</script>
