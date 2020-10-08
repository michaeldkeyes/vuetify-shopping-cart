<template>
  <div>
    <Header />
    <PopularProducts />
    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header";
import PopularProducts from "../components/PopularProducts";
import Footer from "../components/Footer";

export default {
  name: "Home",
  components: {
    Header,
    PopularProducts,
    Footer,
  },
};
</script>

<style>
</style>