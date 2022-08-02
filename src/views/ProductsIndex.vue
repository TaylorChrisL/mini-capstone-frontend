<script>
import axios from "axios";
export default {
  data: function () {
    return {
      products: [],
    };
  },
  created: function () {
    this.indexProducts();
  },
  methods: {
    indexProducts: function () {
      axios.get("/products").then((response) => {
        this.products = response.data;
        console.log("All Products:", this.products);
      });
    },
  },
};
</script>

<template>
  <div v-for="product in products" :key="product.id">
    <h1>{{ product.name }}</h1>
    <h4>{{ product.price }}</h4>
  </div>
</template>
