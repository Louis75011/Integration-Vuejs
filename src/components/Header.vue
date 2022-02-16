<template>
<header>
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
</template>

<script>
export default {
    name: 'Header'
  }
</script>

<style>

</style>