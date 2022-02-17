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

        <ExpandBox title="Suivi commande">
          <div class="order-tracking">
            <div class="step">
              <img src="/assets/Group1.svg" />
              <img class="box" :src="data.status >= 1 ? '/assets/box-checked.png' : '/assets/box.png'" alt="box">
            </div>
            <img class="arrow" src="/assets/blue-arrow.png" alt="arrow">
            <div class="step">
              <img src="/assets/Group2.svg" />
              <img class="box" :src="data.status >= 2 ? '/assets/box-checked.png' : '/assets/box.png'" alt="box">
            </div>
            <img class="arrow" src="/assets/blue-arrow.png" alt="arrow">
            <div class="step">
              <img src="/assets/Group3.svg" />
              <img class="box" :src="data.status >= 3 ? '/assets/box-checked.png' : '/assets/box.png'" alt="box">
            </div>
            <img class="arrow" src="/assets/blue-arrow.png" alt="arrow">
            <div class="step">
              <img src="/assets/Group4.svg" />
              <img class="box" :src="data.status >= 4 ? '/assets/box-checked.png' : '/assets/box.png'" alt="box">
            </div>
          </div>
        </ExpandBox>

        <ExpandBox title="Informations sur les retours">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
          quo tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
        </ExpandBox>
      </div>

      <aside>
        <div class="container-aside">
          <p>ARTICLES ({{totalArticles}})</p>
          <div class="list-articles">
            <div class="container-article" v-for="article in data.articles" :key="article.id">
              <img v-bind:src="article.image" alt="mattress, duvet, pillow">
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
        </div>
      </aside>
    </section>

    <!-- Other menus -->
    <Title>Informations sur la livraison</Title>
    <div class="container-delivery">
      <div class="container-section">
        <h3 class="bold">Adresse de collecte</h3>
        <p>{{data.pickupAddress.name}}</p>
        <p>{{data.pickupAddress.address}}</p>
        <p>{{data.pickupAddress.city}}</p>
        <p>{{data.pickupAddress.zipCode}}</p>
        <p>{{data.pickupAddress.country}}</p>
      </div>

      <div class="container-section">
        <h3 class="bold">Vos coordonnées</h3>
        <p>{{data.userContact.name}}</p>
        <p>{{data.userContact.phone}}</p>
      </div>

      <div class="container-section">
        <h3 class="bold">Livraison estimée</h3>
        <p>jeudi 9 mai 2019</p>
      </div>

      <div class="container-section">
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
      <p><span>Sous-total</span> <span>{{totalPrice}}</span></p>
      <p><span>Livraison</span> <span>{{data.deliveryCharges > 0 ? data.deliveryCharges : "GRATUITE"}}</span></p>
      <p class="bold"><span>TOTAL :</span> <span>{{totalPrice + data.deliveryCharges}}</span></p>
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
    padding: 0 4.5rem;

    @media (max-width: 640px) {
      padding: 0;
    }

    h3 {
      text-transform: uppercase;
    }

    /* Items for sale */
    .delivery-articles {
      display: flex;
      gap: 2.5rem;
      font-size: 13px;

      @media (max-width: 640px) {
        flex-direction: column;
        padding: 0 2rem;
      }

      .order-tracking {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-wrap: wrap;
        padding: 1rem 0;
        gap: 1rem;

        @media (max-width: 768px) {
          flex-direction: column;
          align-items: center;
        }

        .step {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          align-items: center;
          gap: 2rem;
          height: 150px;
        }

        .box {
          width: 32px;
        }

        .arrow {
          display: block;
          width: 32px;
          margin-top: 1rem;

          @media (max-width: 768px) {
            transform: rotate(90deg);
            margin: 1.5rem 0;
          }
        }
      }

      .delivery,
      aside {
        flex: 1;
      }

      .list-articles {
        display: flex;
        flex-direction: column;
        gap: 1.5rem;
      }

      .container-article {
        display: flex;

        padding: 1rem;
        box-shadow: 2px 2px 10px silver;

        h3 {
          margin: 0;
        }

        img {
          height: 120px;
        }

        .container-text {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          margin-left: 1rem;
        }

        .container-size-quantity p {
          margin: 0;
        }
      }

    }

    /* Delivery informations */
    .container-delivery {
      margin: 0 auto;
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      box-shadow: 2px 2px 10px silver;

      @media (max-width: 768px) {
        flex-direction: column;
      }

      .container-section {
        flex: 1;

        @media (max-width: 768px) {
          flex: unset;
        }

        &:not(:first-child) {
          padding-left: 1rem;
          border-left: 2px solid silver;

          @media (max-width: 768px) {
            padding-left: 0;
            border-left: none;
            padding-top: 1rem;
            border-top: 2px solid silver;
          }
        }

        &:not(:last-child) {
          padding-right: 1rem;

          @media (max-width: 768px) {
            padding-right: unset;
            padding-bottom: 1rem;
          }
        }

        h3 {
          margin-top: 0;
        }

        p {
          margin: 0;
        }
      }
    }

    /* Card payment VISA */
    .container-pay {
      margin: 0 auto;
      padding: 1rem;
      display: flex;
      align-items: center;
      box-shadow: 2px 2px 10px silver;

      @media (max-width: 640px) {
        margin: 0 2rem;
      }

      img {
        height: 40px;
      }

      .placing {
        margin-left: 1rem;
      }
    }

    /* Price total */
    .container-total {
      display: flex;
      flex-direction: column;
      box-shadow: 2px 2px 10px silver;
      padding: 1rem;
      gap: 0.75rem;

      @media (max-width: 640px) {
        margin: 0 2rem;
      }

      p {
        display: flex;
        justify-content: space-between;
        flex: 1;
        width: 220px;
        margin: 0 auto;

        @media (max-width: 640px) {
          width: 100%;
          padding: 0 1rem;
        }
      }
    }
  }
</style>