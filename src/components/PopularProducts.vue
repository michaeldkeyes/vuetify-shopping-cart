<template>
  <v-container mb-12>
    <v-row>
      <v-col sm="10" offset-sm="1" lg="8" offset-lg="2">
        <h2>
          Popular Products
          <v-btn :to="{ name: 'Store' }" color="primary" small text
            >View All</v-btn
          >
        </h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col sm="10" offset-sm="1" lg="8" offset-lg="2">
        <v-row>
          <v-col
            sm="6"
            md="4"
            v-for="product in $store.state.products.slice(0, 3)"
            :key="product.name"
          >
            <VerticalProduct :product="product" :addToCart="addToCart" />
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import VerticalProduct from "./cards/VerticalProduct";

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