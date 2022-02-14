<template>
  <h1>Tediber.</h1>

  <header>
    <nav class="navbar">
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
    </nav>
  </header>

  <main>
    <h2>Suivi de commande</h2>

    <section>
      <div>
        <p>N° de commande : <strong>405560003</strong></p>
        <p>Date de commande : <strong>1 mai 2019</strong></p>
        <p>Date d'expédition : <strong>3 mai 2019</strong></p>

        <p>Suivi de commande</p>
        <img />

        <!-- <svg></svg>
        <svg></svg>
        <svg></svg>
        <svg></svg> -->

        <p>Informations sur les retours</p>
        <img />
      </div>

      <article>
        <p>ARTICLES (4)</p>

        <div class="container">
          <div class="container-article">
            <h3>L'incroyable matelas Tediber</h3>
            <p class="bold">750 €</p>
            <p>TAILLE : 160 x 200 cm</p>
            <p>QTÉ: 1</p>
          </div>

          <div class="container-article">
            <h3>L'incroyable oreiller Tediber</h3>
            <p class="bold">85 €</p>
            <p>TAILLE : 60 x 60 cm</p>
            <p>QTÉ: 2</p>
          </div>

          <div class="container-article">
            <h3>L'incroyable couette Tediber</h3>
            <p class="bold">220 €</p>
            <p>TAILLE : 240 x 220 cm</p>
            <p>QTÉ: 1</p>
          </div>

        </div>

      </article>
    </section>

    <h2>Informations sur la livraison</h2>

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

    <h2>Informations de paiement</h2>

    <section>
      <div class="container-pay">
        <img />
        <span>VISA</span>
      </div>
    </section>


    <h2>Total commande</h2>

    <p>Sous-totale 1130</p>
    <p>Livraison GRATUITE</p>
    <p class="bold">TOTAL : 1130</p>
  </main>

  <footer>
    <h2>Besoin d'aide ?</h2>

    <ul>
      <li>Foire aux questions Tediber</li>
      <li>La garantie Tediber</li>
      <li>Reprise de l'ancienne literie</li>
      <li>Comment faire un retour ?</li>
    </ul>
  </footer>
</template>

<script>
  export default {
    name: 'Index'
  }
</script>

<style scoped lang="scss">
  h2,
  h3,
  li {
    text-transform: uppercase;
  }

  .navbar {
    display: flex;
  }

  .bold {
    font-weight: bold;
  }
</style>