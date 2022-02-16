<template>
  <header>
    <!-- Top of the screen -->
    <nav class="navbar">
      <ul>
        <img src="../assets/tediber.png" alt="tediber, property sale">
        <li>Nos produits</li>
        <li>Le concept</li>
        <li>Avis</li>
        <img class="teddy-icon" src="../assets/teddy-face.png" alt="teddy, logo">
        <li>Pub TV</li>
        <li>Mon compte</li>
        <li>Mag</li>
        <li>Contactez-nous</li>
        <img src="../assets/teddy-bag.png" alt="teddy, bag">
      </ul>
    </nav>

    <!-- <nav class="navbar-mobile">
      <ul>
        <li>Nos produits</li>
        <li>Le concept</li>
        <li>Avis</li>
        <img />
        <li>Pub TV</li>
        <li>Mon compte</li>
        <li>Mag</li>
        <li>Contactez-nous</li>
        <img>
      </ul>
    </nav> -->
  </header>
</template>

<script>
  export default {
    name: 'Header'
  }
</script>

<style scoped lang="scss">
  .navbar ul {
    display: flex;
    justify-content: center;
    align-items: center;
    justify-content: space-around;
    list-style-type: none;
    margin: 0 auto;

    li {
      cursor: pointer;
    }

    .teddy-icon {
      margin: 0 2rem;
    }

    h2,
    h3,
    li {
      text-transform: uppercase;
    }

    img {
      height: 50px;
    }
  }
</style>