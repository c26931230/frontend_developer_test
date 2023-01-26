<template>
<section id="about">
    <div class="wrapper">
      <h3 data-aos="fade-up" data-aos-duration="1500">ABOUT DIGISALAD</h3>
      <div class="video_box" @click="play" data-aos="fade-up" data-aos-duration="1500">
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
      <p class="txt" data-aos="fade-up" data-aos-duration="1500">Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum.
        Duis
        tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu
        tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
        eleifend
        a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam
        consectetur,
        eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie
        faucibus.</p>
      <router-link class="btn" to="/" data-aos="fade-up" data-aos-duration="1500">View More <span>——</span></router-link>
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
    methods:{
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
    mounted() {
    },

}
</script>
<style lang="scss">
// ===about===
#about {
  z-index: 9;
  position: relative;

  .wrapper {
    @include maxWidth();

    h3 {
      @include h3('#ABOUT DIGISALAD', $main_4, $main_5);
      position: relative;
      &:after{
          content: "";
          position:absolute;
          display: block;
          // top: 500%;
          left: 0;
          height: 1px;
          width: 60%;
          background-color: #808080;
          position: absolute;
          transform: translateX(-50%) rotate(90deg);
          top: -200%;
          left: 50%;
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

        .fa-circle-play,
        .fa-circle-pause {
          color: $main_5;
          font-size: 60px;
          @include center();
        }
      }

      .icon_box.active {
        .fa-circle-pause {
          animation: pauseAnimation .5s;
          animation-iteration-count: 1;
          animation-fill-mode: forwards;
        }
      }
    }

    .txt {
      width: 80%;
      margin: 30px auto;
      color: $main_4;
      text-align: center;
      @include text();

    }

    .btn {
      @include btn_rectangle()
    }
  }

}

@keyframes pauseAnimation {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

@media screen and (min-width:768px) {
  #about {
    h3 {
      font-size: 28px;
    }

    .video_box {
      .icon_box {

        .fa-circle-play,
        .fa-circle-pause {
          font-size: 100px;
        }
      }

    }
  }
}
</style>