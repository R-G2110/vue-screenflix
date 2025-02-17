<script>
import { store } from '../data/store';
import Collection from './partials/Collection.vue';
import CallToAction from './partials/CallToAction.vue';

export default {
  name: "Main",
  components: {
    Collection,
    CallToAction
  },
  data() {
    return {
      store
    };
  }
};
</script>

<template>
  <main>
    <Collection type="tv" />
    <Collection type="movie" />
    <CallToAction />
  </main>
</template>

<style lang="scss" scoped>
main {
  margin-top: 200px;
}
</style>
