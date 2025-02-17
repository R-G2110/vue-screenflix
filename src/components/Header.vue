<script>
export default {
  name: "Header",
  created() {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<template>
  <header>
    <div class="container">
      <div class="header-logo">
        <h1 class="logo">Screenflix</h1>
      </div>
      <div class="header-actions">
        <ul>
          <li>
            <span class="material-symbols-outlined triangle">
              change_history
            </span>
            <p>change_history</p>
          </li>
          <li>
            <span class="material-symbols-outlined">
              search
            </span>
            <p>search</p>
          </li>
          <!-- visibile se utente non è loggato -->
          <li>
            <span class="material-symbols-outlined">
              login
            </span>
            <p>sign in / sign up</p>
          </li>
          <!-- visibile se utente è loggato -->
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
  border-bottom: var(--border-width) solid var(--border-color);
  display: flex;
  align-items: center;
  overflow: hidden;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  background-color: var(--color-black);
  position: fixed; // Fissa l'header in alto
  top: 0;
  left: 0;
  z-index: 1000; // Assicura che rimanga sopra gli altri elementi

  .container {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    align-items: center;
    width: 93%;
  }

  .logo {
    font-weight: 900;
    font-size: var(--font-lg);
    color: var(--color-red);
    cursor: pointer;
    transition: all 0.3s ease-in-out;

    &:hover {
      color: var(--color-white);
    }
  }

  .header-menu {
    width: 75%;
  }

  .header-actions {
    li {
      padding: 10px 15px;
      text-align: center;
      text-transform: capitalize;

      .triangle {
        display: inline-block;
        transform: rotate(180deg); /* Ruota di 180 gradi */
      }

      span {
        font-size: var(--font-lg);
      }
      p {
        margin-top: -10px;
        font-size: var(--font-xxs);
      }
    }
  }
}

</style>
