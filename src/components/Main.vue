<script>
import Collection from './partials/Collection.vue';
import CallToAction from './partials/CallToAction.vue';

export default {
  name: "Main",
  components: {
    Collection,
    CallToAction
  },
  created() {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<template>
  <main>
    <Collection/>
    <Collection/>
    <Collection/>
    <Collection/>
    <Collection/>
    <Collection/>
    <Collection/>
    <CallToAction/>
  </main>
</template>

<style lang="scss" scoped>
main {

}
</style>