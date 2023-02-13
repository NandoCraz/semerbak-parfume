<template>
  <HeaderComp />
  <HeroComp />
  <ContentComp />
  <FooterComp />
  <PreLoader />
</template>

<script>
import HeaderComp from "./components/partials/HeaderBar.vue";
import HeroComp from "./components/partials/HeroComp.vue";
import ContentComp from "./components/layouts/ContentComp.vue";
import FooterComp from "./components/partials/FooterComp.vue";
import PreLoader from "./components/partials/PreLoader.vue";
export default {
  name: "App",
  components: {
    HeaderComp,
    HeroComp,
    ContentComp,
    FooterComp,
    PreLoader,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
