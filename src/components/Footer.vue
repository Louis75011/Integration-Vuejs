<template>
  <footer>
    <!-- Bottom of the screen -->
    <h2>Besoin d'aide ?</h2>
    <img src="../assets/triangles.png" alt="decoration, yellow">

    <ul>
      <div class="informations">
        <li>Foire aux questions Tediber</li>
        <img src="../assets/menu-footer.png" alt="button">
      </div>

      <div class="informations">
        <li>La garantie Tediber</li>
        <img src="../assets/menu-footer.png" alt="button">
      </div>

      <div class="informations">
        <li>Reprise de l'ancienne literie</li>
        <img src="../assets/menu-footer.png" alt="button">
      </div>

      <div class="informations">
        <li>Comment faire un retour ?</li>
        <img src="../assets/menu-footer.png" alt="button">
      </div>
    </ul>
  </footer>
</template>

<script>
  export default {
    name: 'Footer'
  }
</script>

<style scoped lang="scss">
  footer {
    img {
      height: 20px;
    }

    .informations {
      display: flex;
    }

    h2,
    h3,
    li {
      text-transform: uppercase;
    }
  }
</style>