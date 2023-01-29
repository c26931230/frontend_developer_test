<template>
  <section id="about">
    <div class="wrapper">
      <h3 data-aos="fade-down" data-aos-duration="1500">&nbsp;ABOUT DIGISALAD&nbsp;&nbsp;</h3>
      <div class="video_box" @click="play" data-aos="fade-up" data-aos-duration="1500">
        <video id="myMovie" width="640" poster="../assets/img/video_thumbnail.png">
          <source src="../assets/video/DigiSalad.mp4">
        </video>
        <div class="icon_box" v-show="isPlay == false">
          <img src="../assets/img/play_btn.png" alt="play">
        </div>
        <div class="icon_box" v-show="isPlay" ref="pauseBtn">
          <img src="../assets/img/pause_btn.png" alt="pause">
        </div>
      </div>
      <p class="txt" data-aos="fade-up" data-aos-duration="1500">Cras quis nulla commodo, aliquam lectus sed, blandit
        augue. Cras ullamcorper bibendum bibendum.
        Duis
        tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu
        tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
        eleifend
        a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam
        consectetur,
        eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie
        faucibus.</p>
      <button class="btn" to="/" data-aos="fade-up" data-aos-duration="1500">
        <span>View More</span>
        <span class="line">—————</span>
      </button>
    </div>
  </section>
</template>
<script>
export default {
  name: 'About',
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
        self.$refs.pauseBtn.classList.remove('active')
      } else {
        myMovie.play()
        self.isPlay = true
        self.$refs.pauseBtn.classList.add('active')
      }
    },
  },
}
</script>
<style lang="scss" scoped>
// ===about===
#about {
  z-index: 9;
  position: relative;
  padding-top: 70px;
  overflow: hidden;

  .wrapper {
    @include maxWidth();

    h3 {
      @include decoWavy();

      &:after {
        // === deco line ===
        @include pseudo(1px, 100px, 50%, -200%);
        background-color: #808080;
        transform: translate(-50%, -50%);
      }
    }
  }
}

.video_box {
  width: 80%;
  margin: 70px auto 0;
  position: relative;

  video {
    width: 100%;
    cursor: pointer;
  }

  .icon_box {
    cursor: pointer;

    img {
      @include center();
      width: 50px;
      transition: 0.4s;

      &:hover {
        transform: translate(-50%, -50%) scale(0.8);
        transition: 0.4s;
      }
    }
  }

  .icon_box.active {
    img {
      animation: pauseAnimation .5s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }
  }
}

.txt {
  @include text();
  width: 80%;
  margin: 30px auto;
  color: $main_4;
  text-align: center;

}

.btn {
  @include btnRectangle();
}

@keyframes pauseAnimation {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

@media screen and (min-width:1024px) {
  .video_box {
    width: 960px;

    .icon_box {

      img {
        width: 112px;
      }
    }
  }

  .txt {
    width: 1007px;
  }
}
</style>