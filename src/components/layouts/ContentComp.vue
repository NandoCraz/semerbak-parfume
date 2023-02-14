<template>
  <main id="main">
    <!-- ======= Produk Section ======= -->
    <ProdukComp />
    <!-- End Produk Section -->

    <!-- ======= Counts Section ======= -->
    <CountComp />
    <!-- End Counts Section -->

    <!-- ======= About Section ======= -->
    <AboutComp />
    <!-- End About Section -->

    <!-- ======= Services Section ======= -->
    <KeunggulanComp />
    <!-- End Sevices Section -->
  </main>
</template>

<script>
import ProdukComp from "../content/ProdukComp.vue";
import AboutComp from "../content/AboutComp.vue";
import CountComp from "../content/CountComp.vue";
import KeunggulanComp from "../content/KeunggulanComp.vue";
export default {
  name: "ContentComp",
  components: {
    ProdukComp,
    AboutComp,
    CountComp,
    KeunggulanComp,
  },
};
</script>

<style></style>
