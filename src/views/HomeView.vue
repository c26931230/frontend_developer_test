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
    <div class="video_box">
      <video id="myMovie" width="640" @click="play" poster="../assets/img/video_thumbnail.png">
        <source src="../assets/video/DigiSalad.mp4">
      </video>
    </div>
    {{ isPlay }}
    <i class="fa-solid fa-circle-play"></i>
    <i class="fas fa-check"></i>
    <!-- <button id="playButton" @click="play">play</button> -->
  </section>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      isPlay: false,
    }
  },
  methods: {
    play() {
      const self = this;
      let myMovie = document.getElementById("myMovie");
      if (!myMovie.paused && !myMovie.ended) {
        myMovie.pause()
        self.isPlay = false
      } else {
        myMovie.play()
        self.isPlay = true
      }
    }
  },
  mounted() {
    const self = this;
    window.addEventListener("scroll", function () {
      let scrollHeight = window.scrollY;
      if (scrollHeight >= 20) {
        self.$store.state.isActive = true;
      }
      else {
        self.$store.state.isActive = false;
      }
    });
  },

}
</script>
<style scoped lang="scss">
@import "@/assets/sass/main.scss";
@import "@/assets/sass/home.scss";
</style>