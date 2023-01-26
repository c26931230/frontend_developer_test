<template>
  <!-- OUR INGRADIENTS -->
  <!-- <section id="ingradients" :style="{
    'padding-top': halfAwardBox + 'px',
    'padding-bottom': halfQuoteBox + 'px',
  
  }"> -->
  <section id="ingradients">
    <div class="wrapper">
      <div class="title_box">
        <h3 data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">&nbsp;OUR INGRADIENTS&nbsp;&nbsp;</h3>
        <p data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">
          Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
          tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
          eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
          eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis.
          Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras
          lobortis molestie faucibus.
        </p>
        <router-link class="btn" to="/" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">OUR SERVICES
          <span>——</span></router-link>
      </div>
      <div class="ingradients_box">
        <div class="item" v-for="i in ingredients" :key="i.id" data-aos="fade-up" data-aos-duration="1500">
          <img :src="require(`../assets/img/${i.image}`)" :alt="i.title">
          <h4>{{ i.name }}</h4>
          <p>
            Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare.
          </p>
          <button>VIEW MORE</button>
        </div>
      </div>
      <router-link to="/" class="ingradient_btn" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">VIEW MORE DIGISALAD’S
        INGRADIENTS</router-link>
    </div>
  </section>
</template>
<script>
export default {
  name: 'Ingradients',
  props: ['halfAwardBox', 'halfQuoteBox'],
  data() {
    return {
      ingredients: [
        {
          id: 1,
          name: 'ux dedign',
          image: 'vegetable.png'
        },
        {
          id: 2,
          name: 'ui dedign',
          image: 'tomato.png'
        },
        {
          id: 3,
          name: 'website development',
          image: 'cheese.png'
        },
        {
          id: 4,
          name: 'mobile app development',
          image: 'cucumber.png'
        },
        {
          id: 5,
          name: 'ecommerce',
          image: 'orange.png'
        },
        {
          id: 6,
          name: 'customer loyalty',
          image: 'kiwi.png'
        },
        {
          id: 7,
          name: 'digital transformation',
          image: 'watermelon.png'
        },
        {
          id: 8,
          name: 'digital marketing',
          image: 'corn.png'
        },
        {
          id: 9,
          name: 'branding',
          image: 'apple.png'
        },
      ]
    }
  },
  methods: {
  },
  mounted() {
  },

}
</script>
<style lang="scss" scoped>
// ===ingradients===
#ingradients {
  background-color: $main_5;
  border-radius: 50px 0 50px 0;
  padding-top: 250px;
  padding-bottom: 300px;
  .wrapper {
    width: 100%;
    margin: 0 auto 1000px;
    @include maxWidth();
    padding: 0 10px;
    // border: 1px solid red;

    .title_box {
      margin-bottom: 85px;
      margin-top: 100px;

      h3 {
        @include decoWavy($main_3,$main_6);
        margin-bottom: 70px;
      }

      p {
        text-align: center;
        color: $main_3;
        @include text();
        margin-bottom: 45px;

      }

      .btn {
        @include btn_rectangle($main_6, $main_3);
      }
    }
  }

  .ingradients_box {
    @include flex();
    justify-content: space-between;
    color: $main_3;

    .item {
      width: 100%;
      @include flex();
      flex-direction: column;
      align-items: center;
      justify-content: space-evenly;
      position: relative;
      padding: 30px 25px;

      img {
        display: block;
        width: 30%;
        margin-bottom: 20px;
      }

      h4 {
        text-align: center;
        margin-bottom: 20px;
        font-weight: 700;
        font-size: 20px;
        line-height: 24px;
        letter-spacing: 2px;
        text-transform: uppercase;
        align-self: center;
      }

      p {
        text-align: center;
        @include text();
        margin-bottom: 20px;
      }

      button {
        display: block;
        outline: none;
        background-color: transparent;
        padding: 15px 25px;
        color: $main_3;
        border-radius: 30px;
        font-weight: 700;
        font-size: 14px;
        letter-spacing: 2.22px;
        cursor: pointer;
        border: 2px solid $main_3;
      }
    }
  }

  .ingradient_btn {
    font-weight: 700;
    font-size: 12px;
    line-height: 22px;
    letter-spacing: 2px;
    color: $main_3;
    position: relative;
    display: block;
    width: fit-content;
    margin: 0 auto;
    z-index: 2;
    position: relative;
    text-align: center;
    margin-bottom: 100px;

    &::before {
      content: "#VIEW MORE DIGISALAD’S INGRADIENTS";
      position: absolute;
      color: transparent;
      text-decoration: underline 5px $main_7;
      left: 0;
      bottom: 7px;
      z-index: -1;
      white-space: pre-wrap;
      width: fit-content;
      white-space: nowrap;
    }
  }
}

@media screen and (min-width:387px) {
  #ingradients {
    .wrapper {
      .ingradient_btn {
        &::before {
          white-space: nowrap;
          text-decoration-thickness: 10px;
          left: -2%;
          width: 104%;
        }
      }
    }

  }
}

@media screen and (min-width:768px) {
  #ingradients {
    padding-bottom: 250px;
    .wrapper {
      width: 80%;
      .ingradients_box {
        .item {
          width: 48%;

          button {
            padding: 20px 35px;
          }
        }
      }
    }
  }
}

@media screen and (min-width:1024px) {
  #ingradients {
    padding-top: 150px;
    padding-bottom: 300px;
    .wrapper {
      .ingradients_box {
        .item {
          width: 33.33%;
        }
      }
    }
  }
}
</style>