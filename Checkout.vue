<template>
  <div>
    <h2>Checkout</h2>
    <h3>Cart -</h3>
    <div v-for="item in cart" :key="item.id">
      <br>
      {{ item.title }} <button @click="removeProduct(item)">Remove</button>
      <br>
    </div>
    <p>
      Name: <input v-model="name" />
      Phone: <input v-model="address" />
      <br>
      <br>
      <button>Submit Order</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: ["cart"],
  data() {
    return {
      name: "",
      address: "",
    };
  },
  methods: {
    removeProduct(item) {
        this.$emit("removeProduct", item);
      }
    },
};
</script>