<template>
<section id="award_box" ref="award_box">
      <div class="wrapper">
        <div class="txt_box">
          <h3 data-aos="fade-up" data-aos-duration="1500">AWARDS</h3>
          <p data-aos="fade-up" data-aos-duration="1500">Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
            eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. </p>
        </div>
        <div class="img_box">
          <img src="../assets/img/awards.png" alt="Asia Smart App Awards" v-for="i in 4" data-aos="fade-up" data-aos-duration="1500">
        </div>
      </div>
</section>
</template>
<script>
export default {
    name: 'Awards',
    props:['receiveAwardHeight'],
    data() {
        return {
          halfAwardBox:''
        }
    },
    methods:{
      translate(){
        let awardBoxHeight = this.$refs.award_box.clientHeight;
        this.halfAwardBox = awardBoxHeight / 2;
        this.receiveAwardHeight(this.halfAwardBox)
      }
    },
    mounted() {
    //  const self = this;
    //  window.addEventListener("resize", function () {
    //   self.translate();
    // })
    // this.translate();
    const self = this;
    this.$nextTick(() => {
        self.translate();
    });
    window.addEventListener("resize", function () {
        self.translate();
    });
    },

}
</script>
<style lang="scss" scoped>
// ===award_box===
#award_box {
  position: relative;
  transform: translateY(50%);
  margin-bottom: 50px;
  max-width: 1440px;
  margin: 0 auto;

  .wrapper {
    width: 90%;
    margin-left: auto;
    // max-width: 1200px;
    background-color: $main_3;
    padding: 30px;
    border-radius: 50px 0 50px 50px;

    .txt_box {
      h3 {
        @include h3('#AWARDS', $main_4, $main_5)
      }

      p {
        margin-top: 45px;
        color: $main_4;
        @include text();
      }
    }

    .img_box {
      position: relative;
      padding: 30px 0;

      img {
        width: 50%;
        padding-right: 10px;
        padding-bottom: 10px;
      }
    }
  }
}

@media screen and (min-width:768px) {
  #award_box {
    .wrapper {
      margin-left: auto;

      .img_box {
        img {
          max-width: 360px;
        }
      }
    }
  }
}

@media screen and (min-width:1024px) {
  #award_box {
    .wrapper {
      @include flex();
      align-items: center;

      .txt_box {
        width: 50%;
        padding-right: 37px;
      }

      .img_box {
        width: 50%;

        img {
          max-width: 300px;
          padding: 18px;
        }
      }
    }
  }
}

</style>