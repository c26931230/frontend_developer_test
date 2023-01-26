<template>
    <section id="club_box">
        <div class="num_box">
            <span>0{{ (idx) }}</span>
            <span></span>
            <span>04</span>
        </div>
        <div class="slider_box" ref="slider_box" :style="{
            transform: `translateX(${x}vw)`
        }">
            <div class="wrapper">
                <div class="item" v-for="i in 1">
                    <div class="img_box">
                        <img src="../assets/img/club_bg.png" alt="LP club mobile app">
                        <router-link to="/" class="btn">VIEW PROJECT<span>——</span></router-link>
                    </div>
                    <div class="txt_box">
                        <h4>HIGHLIGHTED SHOWCASE</h4>
                        <h3>LP CLUB MOBILE APP</h3>
                        <p>Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum
                            bibendum. Duis
                            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at
                            semper turpis.
                            Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim
                            nunc. Donec
                            elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia
                            sem
                            elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac
                            rhoncus neque
                            eros nec lacus. Cras lobortis molestie faucibus.</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="ctr_box">
            <button :disabled="idx == 1 ? true : false" @click="x += 100; idx -= 1">
                <img src="../assets/img/left.png" alt="left_btn">
            </button>
            <button :disabled="idx == 4 ? true : false" @click="x -= 100; idx += 1">
                <img src="../assets/img/right.png" alt="right_btn">
            </button>
        </div>
    </section>
</template>
<script>
export default {
    name: 'Club',
    data() {
        return {
            x: 0,
            idx: 1,
        }
    },
    methods: {
    },
    mounted() {
    },

}
</script>
<style lang="scss" scoped>
#club_box {
  overflow: hidden;
  padding: 100px 0;
  position: relative;
  z-index: 9;
  // .num_box{
  //   width: 54px;
  //   height: 54px;
  //   border: 1px solid red;
  // }
  .num_box {
    // border: 1px solid red;
    color: $main_3;
    font-weight: 600;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 2.22222px;
    width: 54px;
    height: 54px;
    position: relative;
    // margin-left: auto;
    position: absolute;
    transform: translateX(-50%);
    left: 90%;
    top: 10%;
    span{
      position:absolute;
      &:nth-child(1){
        top: 0;
        left: 0;
      }
      &:nth-child(2){//line
        height: 1px;
        width: 105%;
        background-color: $main_5;
        display: block;
        transform: rotate(-45deg);
        top: 50%;
      }
      &:nth-child(3){
        bottom: 0;
        right: 0;
      }
    }
  }

  &:after {
    content: '';
    width: 100%;
    height: 100%;
    display: block;
    position: absolute;
    top: 0px;
    left: 0px;
    z-index: -1;
    background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)), url(../assets/img/club_bg.png);
    background-size: cover;
    background-position: bottom;
    background-repeat: no-repeat;
    filter: blur(10px);
  }

  .ctr_box {
    width: 90%;
    @include center();
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    button {
      background-color: transparent;
      border: none;
    }

    img {
      cursor: pointer;
    }
  }

  .slider_box {
    transition: 1s;
    @include maxWidth();
    border: 1px solid red;

    .wrapper {
      // width: 400%;
      display: flex;

      .item {
        @include flex();
        display: inline-block;
        align-items: center;
        justify-content: center;
        padding: 10px 0;
        margin: 0 auto;

        .img_box {
          width: 100%;
          position: relative;
          padding: 30px;

          img {
            width: 70%;
            border-radius: 50px;
            display: block;
            margin: 0 auto 30px;
          }

          .btn {
            @include btn_rectangle($main_5,$main_3,'large');
          }
        }

        .txt_box {
          width: 100%;
          padding: 30px;
          text-align: center;
          order: -1;
          max-height: 300px;
          h4 {
            font-weight: 700;
            font-size: 16px;
            line-height: 19px;
            letter-spacing: 2.22222px;
            color: $main_3;
            margin-bottom: 20px;
          }

          h3 {
            font-weight: 700;
            font-size: 20px;
            line-height: 34px;
            letter-spacing: 3.63636px;
            position: relative;
            width: fit-content;
            margin: 0 auto 40px;
            color: $main_3;
            display: block;
            z-index: 3;

            &::after {
              content: "";
              height: 6px;
              background-color: $main_5;
              position: absolute;
              display: block;
              width: 104%;
              left: -2%;
              bottom: 6px;
              z-index: -1;
            }
          }

          p {
            @include text(24px);
            color: $main_3;
            // width: 80%;
            margin: 0 auto;
            border: 1px solid red;
            display: none;
          }
        }

      }
    }
  }
}

@media screen and (min-width:768px) {
  #club_box {
    .ctr_box {
      @include maxWidth(1500px);

      img {
        display: block;
        z-index: 1000;
      }
    }

    .slider_box {
      .wrapper {
        .item {
          width: 90%;
          @include maxWidth();
          display: flex;
          flex-wrap: wrap;

          .img_box {
            width: 40%;
            margin-bottom: 0;

            img {
              margin-bottom: 0;
            }

            .btn {
              position: absolute;
              bottom: -5%;
              right: -5%;
            }
          }

          .txt_box {
            width: 50%;
            order: 1;
            text-align: left;
            padding: 30px 60px 30px 30px;

            // h4{}
            h3 {
              margin-left: 0;
            }

            p{
              display: block;
            }
          }

        }
      }
    }
  }
}
</style>