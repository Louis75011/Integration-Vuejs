<template>
  <main>
    <!-- Middle of the screen -->
    <h2>Suivi de commande</h2>
    <img src="../assets/triangles.png" alt="decoration, yellow">

    <section class="delivery-articles">
      <div class="delivery">
        <div class="notation">
          <p>N° de commande : <strong>405560003</strong></p>
          <p>Date de commande : <strong>1 mai 2019</strong></p>
          <p>Date d'expédition : <strong>3 mai 2019</strong></p>
        </div>

        <div class="menu-top">
          <p>Suivi de commande</p>
          <img src="../assets/menu-main.png" alt="button">
        </div>

        <!-- <div class="menu-middle">
          <img src="../assets/blue-arrow.png" alt="button">
          <svg></svg>
        <svg></svg>
        <svg></svg>
        <svg></svg>
        </div> -->

        <div class="menu-bottom">
          <p>Informations sur les retours</p>
          <img src="../assets/menu-footer.png" alt="button">
        </div>
      </div>

      <article>
        <p>ARTICLES (4)</p>

        <div class="container">
          <div class="container-article">
            <img src="../assets/tediber-material-01.jpg" alt="mattress">
            <h3>L'incroyable matelas Tediber</h3>
            <p class="bold">750 €</p>
            <p>TAILLE : 160 x 200 cm</p>
            <p>QTÉ: 1</p>
          </div>

          <div class="container-article">
            <img src="../assets/tediber-material-02.jpg" alt="pillow">
            <h3>L'incroyable oreiller Tediber</h3>
            <p class="bold">85 €</p>
            <p>TAILLE : 60 x 60 cm</p>
            <p>QTÉ: 2</p>
          </div>

          <div class="container-article">
            <img src="../assets/tediber-material-03.jpg" alt="duvet">
            <h3>L'incroyable couette Tediber</h3>
            <p class="bold">220 €</p>
            <p>TAILLE : 240 x 220 cm</p>
            <p>QTÉ: 1</p>
          </div>
        </div>
      </article>
    </section>

    <!-- Other menus -->
    <h2>Informations sur la livraison</h2>
    <img src="../assets/triangles.png" alt="decoration, yellow">

    <div class="container-info">
      <div class="info">
        <h3 class="bold">Adresse de collecte</h3>
        <p>POINT RELAIS</p>
        <p>57 rue Jean Piere Timbaud</p>
        <p>Paris</p>
        <p>75011</p>
        <p>France</p>
      </div>

      <div class="info">
        <h3 class="bold">Vos coordonnées</h3>
        <p>Shannon Honniball</p>
        <p>0664262272</p>
      </div>

      <div class="info">
        <h3 class="bold">Livraison estimée</h3>
        <p>jeudi 9 mai 2019</p>
      </div>

      <div class="info">
        <h3 class="bold">Mode de livraison</h3>
        <p>livraison standard en point relais</p>
      </div>
    </div>

    <div class="payment">
      <h2>Informations de paiement</h2>
      <img src="../assets/triangles.png" alt="decoration, yellow">
    </div>

    <div class="container-pay">
      <img src="../assets/visa-card.jpg" alt="visa card">
      <span>VISA</span>
    </div>

    <h2>Total commande</h2>
    <img src="../assets/triangles.png" alt="decoration, yellow">

    <p>Sous-totale 1130</p>
    <p>Livraison GRATUITE</p>
    <p class="bold">TOTAL : 1130</p>
  </main>
</template>

<script>
  export default {
    name: 'Main'
  }
</script>

<style scoped lang="scss">
  main {

    h2,
    h3,
    li {
      text-transform: uppercase;
    }

    section img {
      height: 20px;
    }

    section article img {
      height: 80px;
    }

    .delivery-articles {
      display: flex;
      justify-content: center;
    }

    .container-info {
      display: flex;
    }
  }
</style>