<script>
import FooterTop from './partials/FooterTop.vue';
import FooterBottom from './partials/FooterBottom.vue';

export default {
  name: "Footer",
  components: {
    FooterTop,
    FooterBottom
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
  <footer>
    <FooterTop/>
    <FooterBottom/>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  font-size: var(--font-xs);
  background: var(--color-gray-dark);
  //border: 1px solid white;
}
</style>