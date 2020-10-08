<template>
  <v-card outlined>
    <v-img
      :src="require('@/assets/' + product.image + '.jpg')"
      height="200px"
    />
    <v-card-title> {{ product.name }} </v-card-title>
    <v-card-subtitle> ${{ product.price }} </v-card-subtitle>
    <v-card-actions>
      <v-btn @click="addToCart" color="success" outlined
        ><v-icon left small>fa-plus</v-icon>Add to Cart
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    product: Object,
    addToCart: Function,
  },
};
</script>

<style>
</style>