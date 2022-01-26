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
              <tr>
                <td></td>
                <td>Cucumber</td>
                <td>2</td>
                <td class="text-right">20.3</td>
                <td class="text-right">
                  <button class="btn btn-sm btn-danger">
                    <font-awesome-icon icon="trash" />
                  </button>
                </td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td><strong>Total</strong></td>
                <td class="text-right"><strong>€</strong></td>
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
  }
}
</script>
