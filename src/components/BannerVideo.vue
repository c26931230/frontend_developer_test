<template>
<section id="video_box">
    <video autoplay muted loop>
      <source src="../assets/video/DigiSaladWebsiteVideo-v3.mp4" type="video/mp4" />
    </video>
    <div class="info_box" v-show="$store.state.isMenuOpen == false">
      <a href="#" class="logo" data-aos="zoom-in" data-aos-duration="1000">
        <img src="@/assets/img/logo_white.png" alt="digisalad logo" v-show="$store.state.isActive == false">
      </a>
      <h2 data-aos="zoom-in" data-aos-duration="1000">WE CREATE<br>
        AMAZING<br>
        DIGITAL EXPERIENCES
      </h2>
      <div class="salad_box">
        <img src="@/assets/img/salad.png" alt="salad">
        <p>TASTE US NOW!</p>
      </div>
    </div>
    <div class="deco_box" data-aos="fade-up" v-show="$store.state.isMenuOpen == false">
      <p>DIGITAL AGENCY</p>
    </div>
  </section>
</template>
<script>
export default {
    name: 'BannerVideo',
    data() {
        return {
            
        }
    },
    mounted() {
    },

}
</script>
<style lang="scss" scoped>
// ===banner video===
#video_box {
  overflow: hidden;
  width: 100%;
  position: relative;
  height: calc(100vh - 2px);
  top: 0;
  border-radius: 0 0 50px 50px;
  box-sizing: border-box;
  margin-bottom: 70px;

  &::after {
    content: "";
    background-color: #00000030;
    position: absolute;
    display: block;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  video {
    // @include center();
    min-width: 100%;
    min-height: 100vh;
    position: absolute;
    transform: translateX(-50%);
    top: 0;
    left: 50%;
  }

  .info_box {
    @include center();
    @include maxWidth();
    z-index: 9;
    width: 70%;
    text-align: center;
    margin: 30px 0;
    // opacity: 0;//*** */
    .logo {
      width: 40%;
      position: relative;
      display: block;
      margin: 0 auto;

      img {
        width: 100%;
        vertical-align: top;
      }

    }

    h2 {
      padding: 20px 0;
      color: $main_3;
      font-weight: 700;
      font-size: 28px;
      line-height: 50px;
      letter-spacing: 3.16667px;
    }

    .salad_box {
      width: 100%;
      text-align: center;
      margin-top: 60px;

      img {
        width: 50px;
      }

      p {
        color: $main_3;
        font-weight: 700;
        font-size: 14px;
        line-height: 17px;
        padding: 10px 0;
        letter-spacing: 2px;
        // border: 1px solid red;
        // position: relative;
        // width: fit-content;
        // margin: 0 auto;
        // &:after{
        //   content: "";
        //   position:absolute;
        //   display: block;
        //   top: 500%;
        //   left: 0;
        //   height: 1px;
        //   width: 200%;
        //   background-color: #808080;
        //   // transform: rotate(90deg);
        //   position: absolute;
        //   transform: translateX(-50%) rotate(90deg);
        //   top: 50%;
        //   left: 50%;
        // }
      }
    }
  }

  .deco_box {
    // visibility: hidden;//暫時
    p {
      writing-mode: vertical-rl;
      color: $main_3;
      font-size: 16px;
      z-index: 8;
      position: absolute;
      transform: translateY(-50%);
      top: 65%;
      left: 0%;
      white-space: nowrap;
      padding: 0 10px;

      &::after {
        content: "";
        background-color: $main_3;
        position: absolute;
        display: block;
        transform: translateX(-50%);
        left: 50%;
        top: 110%;
        width: 2px;
        height: 70%;
      }
    }
  }
}

@media screen and (min-width:768px) {
  #video_box {
    .info_box {
      text-align: left;
      width: 90%;

      .logo {
        width: 150px;
        margin: 0;
      }

      h2 {
        font-weight: 700;
        font-size: 38px;
        line-height: 70px;
        letter-spacing: 9.16667px;
      }
    }

    .deco_box {
      p {
        top: 50%;
      }
    }
  }
}
</style>