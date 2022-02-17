<template>
  <header>
    <!-- Top of the screen -->
    <nav>
      <button @click="menuOpen = !menuOpen" id="burger">
        <img src="/assets/menu-burger.png" alt="menu">
      </button>

      <img src="/assets/tediber.png" alt="tediber, property sale">
      <ul>
        <li>Nos produits<button><img src="/assets/menu-footer.png" alt="arrow" /></button></li>
        <li>Le concept</li>
        <li>Avis</li>
      </ul>
      <img class="teddy-icon" src="/assets/teddy-face.png" alt="teddy, logo">
      <ul>
        <li>Pub TV</li>
        <li>Mon compte</li>
        <li>Mag</li>
        <li>Contactez-nous</li>
      </ul>
      <img src="/assets/teddy-bag.png" alt="teddy, bag">
    </nav>
  </header>

  <nav v-if="menuOpen === true" id="burger-nav">
    <ul>
      <li>Nos produits</li>
      <li>Le concept</li>
      <li>Avis</li>
      <li>Pub TV</li>
      <li>Mon compte</li>
      <li>Mag</li>
      <li>Contactez-nous</li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name: 'Header',
    data() {
      return {
        menuOpen: true
      }
    }
  }
</script>

<style scoped lang="scss">
  nav {
    padding: 0.5rem;
    box-shadow: 0 2px 6px 0 #ccc;
    gap: 1rem;
    text-transform: uppercase;
    cursor: pointer;
  }

  header nav {
    display: flex;
    justify-content: space-between;
  }

  #burger {
    display: none;
    border: none;
    background: transparent;
    cursor: pointer;

    img {
      height: 40px;
    }

    @media (max-width: 1200px) {
      display: block;
    }
  }

  header nav ul {
    display: flex;
    align-items: center;
    justify-content: space-around;
    list-style-type: none;
    margin: 0 auto;
    gap: 2rem;
    padding-inline-start: 0;

    @media (max-width: 1200px) {
      display: none;
    }

    li {
      display: flex;
      text-align: center;
      cursor: pointer;
      text-transform: uppercase;
      white-space: nowrap;
      gap: 0.25rem;

      button {
        border: none;
        background: transparent;

        img {
          height: 12px;
          cursor: pointer;
          opacity: 0.2;
        }
      }
    }
  }

  .teddy-icon {
    margin: 0 2rem;

    @media (max-width: 1200px) {
      display: none;
    }
  }

  img {
    display: block;
    height: 50px;
  }

  #burger-nav {
    display: none;

    @media (max-width: 1200px) {
      display: flex;
    }

    ul {
      list-style-type: none;
    }
  }
</style>