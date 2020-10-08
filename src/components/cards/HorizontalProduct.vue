<template>
  <v-card class="mb-5 pa-4" outlined min-width="100%">
    <div class="d-flex">
      <div>
        <v-img
          :src="require('@/assets/' + product.image + '.jpg')"
          width="120px"
          height="120px"
        ></v-img>
      </div>
      <div class="d-flex flex-column justify-center">
        <v-card-title class="pt-0">
          {{ product.name }}
        </v-card-title>
        <v-card-subtitle> ${{ product.price }} </v-card-subtitle>
        <v-btn class="ml-4" color="error" outlined small>
          <v-icon small left>fa-minus</v-icon>
          Remove from Cart
        </v-btn>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {
  props: {
    product: Object,
    updateCart: Function,
    btnAction: String,
    i: Number,
  },
};
</script>

<style>
</style>