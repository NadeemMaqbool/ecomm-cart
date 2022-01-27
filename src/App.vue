<template>
  <div id="nav">
    <nav class="navbar navbar-expand-md navbar-dark bg-dark">
      <div class="container">
        <h3>Simple Ecommerce</h3>
        <div
          class="collapse navbar-collapse justify-content-end"
          id="navbarsExampleDefault"
        >
          <ul class="navbar-nav m-auto">
            <li class="nav-item active">
              <router-link to="/products" class="nav-link">
                Products
              </router-link>
            </li>

            <li class="nav-item">
              <router-link to="/cart" class="nav-link">Cart</router-link>
            </li>
          </ul>

          <form class="form-inline my-2 my-lg-0">
            <router-link class="btn btn-success btn-sm ml-3" to="/cart" >
              <i class="fa fa-shopping-cart" ></i> Cart<span class="badge badge-light" >( {{ getCartLength() }} )</span>
            </router-link>
          </form>
        </div>
      </div>
    </nav>
  </div>

  <router-view />
</template>
<script>
export default {
  data () {
    return {
      cart: {},
      cartSize: 0
    }
  },
  methods: {
    getCartLength () {
      return Object.values(
        JSON.parse(localStorage.getItem('cart')) ?? {}
      ).length ?? 0
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FFF;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
