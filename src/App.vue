<script>
import axios from 'axios';

import Header from "./components/Header.vue";
import Hero from './components/Hero.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: "App",
  components: {
    Header,
    Hero,
    Main,
    Footer
  },
  data() {
    return {};
  },
  methods: { },
  mounted() {
  },
};
</script>

<template>
  <Header />
  <Hero />
  <Main />
  <Footer />
</template>

<style lang="scss">
@use './scss/main.scss';

</style>
