<template>
  <!-- OUR INGRADIENTS -->
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
        <button class="btn" to="/" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">
          <span>OUR SERVICES</span>
          <span class="line">———</span>
        </button>
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
        <button class="btn_line" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-50">VIEW
        MORE DIGISALAD’S
        INGRADIENTS</button>
    </div>
  </section>
</template>
<script>
export default {
  name: 'Ingradients',
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

}
</script>
<style lang="scss" scoped>
// ===ingradients===
#ingradients {
  background-color: $main_5;
  border-radius: 50px 0 50px 0;
  padding-top: 250px;
  padding-bottom: 350px;

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
        @include decoWavy($main_3, $main_6);
        margin-bottom: 70px;
      }

      p {
        text-align: center;
        color: $main_3;
        @include text();
        margin-bottom: 45px;

      }

      .btn {
        @include btnRectangle('normal',$main_6, $main_3, $main_3, $main_6);
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
        position: relative;
        overflow: hidden;
        transition: 0.4s transform ease-in-out;

        &::after {
          background-color: #fff;
          border-radius: 30px;
          content: '';
          display: block;
          height: 100%;
          width: 100%;
          position: absolute;
          left: 0;
          top: 0;
          transform: translate(-100%, 0) rotate(10deg);
          transform-origin: top left;
          transition: 0.4s transform ease-out;
          z-index: -1;
        }

        &:hover::after {
          transform: translate(0, 0);
        }

        &:hover {
          border: 2px solid transparent;
          color: $main_5;
          transform: scale(0.98);
        }
      }
    }
  }
  .btn_line{
    border: none;
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
    background: transparent;
    outline: none;
    cursor: pointer;
    transition: 0.4s;
    white-space: nowrap;
    &::after{
      @include pseudo(100%,10px,0,50%);
      background-color: $main_7;
      z-index: -1;
      transition: 0.4s;
    }
    &:hover::after{
      // background-color: #fff;
      height: 5px;
      width: 104%;
      top: 70%;
      left: -2%;
      border-radius: 20px;
    }
    &:hover{
      transform: translateY(10%) scale(1.1);
      transition: 0.4s;
    }
  }
 
}

@media screen and (min-width:322px) {
  #ingradients {
    .wrapper {
      .btn_line{
        font-size: 18px;
      }
    }

  }
}

@media screen and (min-width:768px) {
  #ingradients {
    padding-bottom: 300px;

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
    padding-bottom: 380px;

    .wrapper {
      .ingradients_box {
        margin-bottom: 50px;
        .item {
          width: 33.33%;
        }
      }
    }
  }
}
</style>