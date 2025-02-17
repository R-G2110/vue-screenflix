<script>
import axios from 'axios';
import { store } from './data/store';

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
    return {
      store
    };
  },
  methods: {
    getApi(type) {
      store.movie = [];
      store.tv = [];
      if (store.apiParams.query === ''){
        store.apiUrlBase += store.default;
      } else store.apiUrlBase += store.search
      axios.get(store.apiUrlBase + type, {
        params: store.apiParams
      })
      .then(result => {
        if (store.type === 'multi'){
          result.data.results.forEach(object => {
            if (object.media_type !== 'movie'){
              store.tv.push(object)
            } else {
              store.movie.push(object)
            }
          });
        } else{
          store[type] = result.data.results;
        }
        
      })
      .catch(error => {
      })
    },
    startSearch() {
      this.getApi(store.type);
      store.apiParams.query = '';
      store.type = 'multi';
      store.apiUrlBase = 'https://api.themoviedb.org/3/';
      console.log('store.movie: '+store.movie.length);
      console.log('store.tv: '+store.tv.length);
    },

  },
  mounted() {
    this.startSearch();
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
