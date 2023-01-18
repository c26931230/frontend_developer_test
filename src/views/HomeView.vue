<template>
  <section id="video_box">
    <video autoplay muted loop>
      <source src="../assets/video/DigiSaladWebsiteVideo-v3.mp4" type="video/mp4" />
    </video>
    <div class="info_box">
      <a href="#" class="logo">
        <img src="@/assets/img/logo_white.png" alt="digisalad logo" v-show="$store.state.isActive == false">
      </a>
      <h2>WE CREATE<br>
        AMAZING<br>
        DIGITAL EXPERIENCES
      </h2>
      <div class="salad_box">
        <img src="@/assets/img/salad.png" alt="salad">
        <p>TASTE US NOW!</p>
      </div>
    </div>
    <div class="deco_box">
      <p>DIGITAL AGENCY</p>
    </div>
  </section>
  <section id="about">
    <h3>ABOUT DIGISALAD</h3>
    <div class="video_box" @click="play">
      <video id="myMovie" width="640" poster="../assets/img/video_thumbnail.png">
        <source src="../assets/video/DigiSalad.mp4">
      </video>
      <div class="icon_box" v-show="isPlay == false">
        <i class="fa-solid fa-circle-play"></i>
      </div>
      <div class="icon_box" v-show="isPlay" ref="pauseBtn">
        <i class="fa-solid fa-circle-pause"></i>
      </div>
    </div>
    <p class="txt">Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
      tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu
      tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante, eleifend
      a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam consectetur,
      eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie
      faucibus.</p>
    <router-link class="btn" to="/">View More <span>——</span></router-link>
  </section>
  <div class="main_box" :style="{
    transform: `translateY(${-halfAwardBox}px)`
  }">
    <!-- AWARDS -->
    <section id="award_box" ref="award_box">
      <div class="wrapper">
        <div class="txt_box">
          <h3>AWARDS</h3>
          <p>Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
            eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. </p>
        </div>
        <div class="img_box">
          <img src="../assets/img/awards.png" alt="Asia Smart App Awards" v-for="i in 4">
        </div>
      </div>
    </section>
    <!-- OUR INGRADIENTS -->
    <section id="ingradients" :style="{
      'padding-top': halfAwardBox + 'px'
    }">
      <div class="wrapper">
        <div class="title_box">
          <h3>OUR INGRADIENTS</h3>
          <p>
            Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
            eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
            eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis.
            Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras
            lobortis molestie faucibus.
          </p>
          <router-link class="btn" to="/">OUR SERVICES <span>——</span></router-link>
        </div>
        <div class="ingradients_box">
          <div class="item" v-for="i in ingredients" :key="i.id">
            <img :src="require(`../assets/img/${i.image}`)" :alt="i.title">
            <h4>{{ i.name }}</h4>
            <p>
              Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
              tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare.
            </p>
            <button>VIEW MORE</button>
          </div>
        </div>
        <router-link to="/" class="ingradient_btn">VIEW MORE DIGISALAD’S INGRADIENTS</router-link>
      </div>
    </section>
    <!-- quote -->
    <section id="quote_box">

    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      isPlay: false,
      halfAwardBox: '',
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
    windowScroll() {
      let scrollHeight = window.scrollY;
        if (scrollHeight >= 20) {
          this.$store.state.isActive = true;
        }
        else {
          this.$store.state.isActive = false;
        }
    },
    play() {
      const self = this;
      let myMovie = document.getElementById("myMovie");
      if (!myMovie.paused && !myMovie.ended) {
        myMovie.pause()
        self.isPlay = false
        self.$refs.pauseBtn.classList.remove('active')
      } else {
        myMovie.play()
        self.isPlay = true
        self.$refs.pauseBtn.classList.add('active')
      }
    },
    traslate() {
      let award_boxHeight = this.$refs.award_box.clientHeight;
      this.halfAwardBox = award_boxHeight / 2;
    }
  },
  mounted() {
    const self = this;
    window.addEventListener("scroll", function () {
      self.windowScroll()
    })
    window.addEventListener("resize", function () {
      self.traslate()
    })
    this.traslate()
    this.windowScroll()
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },

}
</script>
<style scoped lang="scss">
@import "@/assets/sass/main.scss";
@import "@/assets/sass/home.scss";
</style>