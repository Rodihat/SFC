<template>
  <div id="app">
    <header>
      <h1>{{ sitename }}</h1>
      <!-- <span v-text=cart></span> -->
      <span>Cart - </span>{{ this.cart.length }}
      <br />
      <br />
      <button>Checkout</button>
    </header>
    <br />
    <lesson-list @addProduct="addToCart"></lesson-list>
    <checkout @removeProduct="removeFromCart" :cart="cart"></checkout>
  </div>
</template>

        <script>
import Checkout from "/Checkout.vue";
import LessonList from "/Products.vue";
export default {
  name: "App",
  components: { LessonList, Checkout },
  data() {
    return {
      sitename: "After School Club",
      cart: [],
    };
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
    },
    removeFromCart(item) {
      const index = this.cart.indexOf(item);
      this.cart.splice(index, 1);
    },
  },
};
</script>