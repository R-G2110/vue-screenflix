<script>
export default {
  name: "FooterBottom",
  data() {
    return {
      selectedLanguage: "eng",
      languages: [
        { code: "eng", label: "English" },
        { code: "ita", label: "Italiano" },
      ],
    };
  },
  methods: {
    changeLanguage(event) {
      this.selectedLanguage = event.target.value;
      console.log("Selected language:", this.selectedLanguage);
    },
  },
};
</script>

<template>
  <div class="footer-bottom">
    <div class="container-md">
      <p>Made with &hearts; by R-G</p>
      <div class="dropdown-container">
        <select v-model="selectedLanguage" @change="changeLanguage">
          <option v-for="lang in languages" :key="lang.code" :value="lang.code">
            {{ lang.label }}
          </option>
        </select>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-bottom {
  height: 100px;

  .container-md {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .dropdown-container {
    position: relative;
    display: inline-block;
  }

  select {
    padding: 5px;
    font-size: 1rem;
    border: 1px solid transparent;
    border-radius: 5px;
    cursor: pointer;
    color: var(--color-gray-dark);
    transition: all 0.3s ease-in-out;
    
    &:hover {
      background-color: var(--color-red);
      color: var(--color-white);
    }

    &:focus {
      outline: none;
      border-color: var(--color-red);
      background-color: var(--color-red);
      color: var(--color-white);
    }
  }
}
</style>
