<template>
  <div>
    <h3>Product Display</h3>
    <v-row>
      <v-col
        sm="6"
        md="4"
        v-for="product in $store.state.products"
        :key="product.name"
      >
        <VerticalProduct :product="product" :addToCart="addToCart" />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import VerticalProduct from "../cards/VerticalProduct";

export default {
  components: {
    VerticalProduct,
  },
  methods: {
    addToCart(index, quantity = 1) {
      this.$store.commit("addItemToCart", { itemId: index, quantity });
      this.$store.commit("updateSnackbar", true);
    },
  },
};
</script>

<style>
</style>