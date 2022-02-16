<template>
  <main>
    <!-- Middle of the screen -->
    <Title>Suivi de commande</Title>
    <section class="delivery-articles">
      <div class="delivery">
        <div class="notation">
          <p>N° de commande : <strong>{{data.orderNumber}}</strong></p>
          <p>Date de commande : <strong>{{renderDate(data.orderDate)}}</strong></p>
          <p>Date d'expédition : <strong>{{renderDate(data.shippingDate)}}</strong></p>
        </div>

        <ExpandBox title="Suivi commande"></ExpandBox>

        <!-- <div class="menu-middle">
          <img src="../assets/blue-arrow.png" alt="button">
          <svg></svg>
        <svg></svg>
        <svg></svg>
        <svg></svg>
        </div> -->

        <ExpandBox title="Informations sur les retours">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
          quo tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
        </ExpandBox>
      </div>

      <aside>
        <p>ARTICLES ({{totalArticles}})</p>

        <div class="container-aside">
          <div class="container-article" v-for="article in data.articles" :key="article.id">
            <img v-bind:src="article.image" alt="mattress">
            <div class="container-text">
              <h3>{{article.title}}</h3>
              <p class="bold">{{article.price}} €</p>
              <div class="container-size-quantity">
                <p>TAILLE : {{article.size.join(" x ")}} cm</p>
                <p>QTÉ: {{article.amount}}</p>
              </div>
            </div>
          </div>
        </div>
      </aside>
    </section>

    <!-- Other menus -->
    <Title>Informations sur la livraison</Title>
    <div class="container-delivery">
      <div class="container-address">
        <h3 class="bold">Adresse de collecte</h3>
        <p>{{data.pickupAddress.name}}</p>
        <p>{{data.pickupAddress.address}}</p>
        <p>{{data.pickupAddress.city}}</p>
        <p>{{data.pickupAddress.zipCode}}</p>
        <p>{{data.pickupAddress.country}}</p>
      </div>

      <div class="container-coordinates">
        <h3 class="bold">Vos coordonnées</h3>
        <p>{{data.userContact.name}}</p>
        <p>{{data.userContact.phone}}</p>
      </div>

      <div class="container-estimated">
        <h3 class="bold">Livraison estimée</h3>
        <p>jeudi 9 mai 2019</p>
      </div>

      <div class="container-method">
        <h3 class="bold">Mode de livraison</h3>
        <p>livraison standard en point relais</p>
      </div>
    </div>

    <div class="payment">
      <Title>Informations de paiement</Title>
    </div>

    <div class="container-pay">
      <img :src="paymentImages[data.paymentType]" :alt="data.paymentType">
      <span class="placing">{{data.paymentType}}</span>
    </div>

    <Title>Total commande</Title>
    <div class="container-total">
      <p>Sous-total {{totalPrice}}</p>
      <p>Livraison {{data.deliveryCharges > 0 ? data.deliveryCharges : "GRATUITE"}}</p>
      <p class="bold">TOTAL : {{totalPrice + data.deliveryCharges}}</p>
    </div>
  </main>
</template>

<script>
  import data from '../data/db.json'
  import Title from './Title.vue'
  import ExpandBox from './ExpandBox.vue';

  export default {
    name: "Main",
    data() {
      return {
        data,
        paymentImages: {
          VISA: "/assets/visa-card.jpg",
        },
        // Calcule le nombre total d'éléments
        totalArticles: data.articles.reduce((total, element) => {
          return total + element.amount;
        }, 0),
        // Calcule le prix total
        totalPrice: data.articles.reduce((total, element) => {
          return total + element.amount * element.price;
        }, 0)
      };
    },
    methods: {
      // Renvoie la date en version française
      renderDate(dateString, weekday = false) {
        const d = new Date(dateString);
        const year = d.getFullYear();
        const month = [
          "janvier", "février", "mars", "avril", "mai", "juin",
          "juillet", "août", "septembre", "octobre", "novembre", "décembre"
        ][d.getMonth()];
        const day = d.getDate();
        let dow = "";
        if (weekday) {
          dow = [
            "dimanche", "lundi", "mardi", "mercredi",
            "jeudi", "vendredi", "samedi",
          ][d.getDay()];
        }
        return [dow, day, month, year].join(" ").trim();
      }
    },
    components: {
      Title,
      ExpandBox
    }
  }
</script>

<style scoped lang="scss">
  main {
    h3 {
      text-transform: uppercase;
    }

    /* Items for sale */
    .delivery-articles {
      /* width: 80%; */
      display: flex;    
      font-size: 13px;

      .delivery,
      aside {
        flex: 1;
      }

      aside .container-aside {
        display: flex;
        flex-direction: column;

        .container-article {
          display: flex;
          margin: 1rem;
          padding: 1rem;
          box-shadow: 2px 2px 2px 2px gray;
          border-radius: 2px;

          img {
            height: 200px;
          }

          .container-text {
            margin-left: 1rem;
          }
        }
      }
    }

    /* Delivery informations */
    .container-delivery {
      width: 80%;
      margin: 0 auto;
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      box-shadow: 2px 2px 2px 2px gray;

      .container-coordinates, .container-estimated, .container-method {
        border-left: 2px solid gray;
      }
    }

    /* Card payment VISA */
    .container-pay {
      width: 80%;
      margin: 0 auto;
      padding: 1rem;
      display: flex;
      align-items: center;
      box-shadow: 2px 2px 2px 2px gray;

      .placing {
        margin-left: 1rem;
      }
    }

    /* Price total */
    .container-total {
      flex-direction: column;
      text-align: center;
      width: 80%;
      margin: 0 auto;
      padding: 1rem;
      box-shadow: 2px 2px 2px 2px gray;
    }
  }
</style>