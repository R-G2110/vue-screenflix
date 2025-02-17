<script>
export default {
  name: "FooterTop",
  created() {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<template>
  <div class="footer-top">
    <div class="container-md">
      <div class="col">
        <h4>navigation</h4>
        <a>browse new trends</a>
        <a>browse popular</a>
        <a>browse simulcasts</a>
        <a>release calendar</a>
        <a>news</a>
      </div>
      <div class="col">
        <h4>faq</h4>
        <a>investor relations</a>
        <a>how to watch screenflix</a>
        <a>about the company</a>
      </div>
      <div class="col">
        <h4>screenflix</h4>
        <a>about</a>
        <a>help center</a>
        <a>terms of use</a>
        <a>privacy policy</a>
        <a>cookie consent tool</a>
        <a>download app</a>
      </div>
      <div class="col">
        <h4>account</h4>
        <a>create account</a>
        <a>login</a>
      </div>
    </div>
  </div>
</template>



<style lang="scss" scoped>
.footer-top {
  height: 400px;

  .container-md {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    padding: 50px 0;
    border-bottom: var(--border-width) solid var(--border-color-light);

    .col {
      display: flex;
      flex-direction: column;
      //border: var(--border-width) solid var(--border-color);

      h4 {
        margin-bottom: 10px;
      }

      a {
        position: relative;
        text-decoration: none;
        color: white;
        cursor: pointer;
        padding-bottom: 10px;
        display: inline-block; 
        max-width: max-content;

        &::after {
          content: "";
          position: absolute;
          left: 0;
          bottom: 10px;
          width: 0%;
          height: 2px;
          background: linear-gradient(to right, var(--color-red), transparent);
          transition: width 0.7s ease-in-out, opacity 0.7s ease-in-out;
          opacity: 0;
        }

        &:hover::after {
          width: 100%;
          opacity: 1;
        }

        &:hover {
          color: var(--color-red);
        }

      }

      h4, a {
        text-transform: capitalize;
      }
    }
  }
}

</style>