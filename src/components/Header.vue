<script>
export default {
  name: "Header",
  data() {
    return {
      isScrolled: false, // Stato per controllare lo scroll
    };
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > window.innerHeight; // Se supera 100vh, attiva la classe
    },
  },
};
</script>

<template>
  <header :class="{ 'small-header': isScrolled }">
    <div class="container">
      <div class="header-logo">
        <h1 class="logo">Screenflix</h1>
      </div>
      <div class="header-actions">
        <ul>
          <li>
            <span class="material-symbols-outlined">
              search
            </span>
            <p>search</p>
          </li>
          <li>
            <span class="material-symbols-outlined">
              login
            </span>
            <p>sign in / sign up</p>
          </li>
          <li>
            <span class="material-symbols-outlined">
              person
            </span>
            <p>name</p>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  width: 100%;
  height: var(--header-height);
  border-bottom: var(--border-width) solid var(--border-color-dark);
  display: flex;
  align-items: center;
  overflow: hidden;
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.1);
  background-color: var(--color-black);
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  transition: all 0.3s ease-in-out;

  .container {
    display: flex;
    height: 100%;
    justify-content: space-between;
    align-items: center;
    width: 93%;
    margin: 0 auto;
  }

  .header-logo {
    margin-top: 10px;
    font-size: var(--font-lg);
    color: var(--color-red);
    cursor: pointer;
    transition: all 0.3s ease-in-out;
    
    &:hover {
      color: var(--color-white);
    }
  }

  .header-actions {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    
    ul {
      display: flex;
      align-items: center;
      height: 100%;
      
      li {
        width: 100px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100%;
        text-align: center;
        text-transform: capitalize;

        span {
          font-size: var(--font-xl);
          transition: all 0.3s ease-in-out;
        }

        p {
          font-size: var(--font-xs);
          transition: all 0.3s ease-in-out;
        }
      }
    }
  }
}

/* Effetto rimpicciolimento */
.small-header {
  height: 60px;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.3);
  

  .header-logo {
    font-size: var(--font-md);
  }
  .header-actions {
    span {
      font-size: var(--font-lg);
    }
    
    p {
      margin-top: -2px;
      font-size: var(--font-xxs);
    }
  }
}

</style>
