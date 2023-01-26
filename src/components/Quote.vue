<template>
  <!-- quote -->
  <section id="quote_box" ref="quote_box">
      <div class="wrapper">
        <div class="img_box">
          <img src="../assets/img/founder.png" alt="Tony Ng" >
          <h3>TONY NG</h3>
          <p><i>Founder & Creative Director</i></p>
        </div>
        <div class="txt_box">
          <img src="../assets/img/quote_icon.png" alt="quote">
          <p>A great digital work isn’t about designing beautiful pages purely. It is about context - how do we deliver
            the <strong> experience to the right person at the right time.</strong>The most important thing is that your
            work can engage customers at anytime, anywhere and let users experience an entire amazing digital journey.
          </p>
        </div>
      </div>
    </section>
</template>
<script>
export default {
    name: 'Quote',
    props:['receiveQuoteHeight'],
    data() {
        return {
          halfQuoteBox:'',
        }
    },
    methods:{
      translate(){
        let quoteBoxHeight = this.$refs.quote_box.clientHeight;
       this.halfQuoteBox = quoteBoxHeight / 2;
       this.receiveQuoteHeight(this.halfQuoteBox)
      }
    },
    mounted() {
      const self = this;
     window.addEventListener("resize", function () {
      self.translate();
    })
    this.translate();
    },

}
</script>
<style lang="scss" scoped>
// === quote_box ===
#quote_box {
  margin-top: 50px;
  max-width: 1440px;
  margin: 0 auto;
  background-color: $main_3;
  width: 100%;

  .wrapper {
    border-radius: 0 50px 50px 50px;
    width: 90%;
    background-image: linear-gradient(0deg, rgba(88, 88, 128, 0.8), rgba(88, 88, 128, 0.8)), url(../assets/img/quote_bg.png);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    padding: 30px;
    transform: translateY(-50%);

    .img_box {
      text-align: center;
      position: relative;
      color: $main_3;
      margin-bottom: 30px;

      img {
        width: 50%;
        max-width: 100px;
        display: block;
        margin: 0 auto 10px;
        max-width: 150px;
      }

      h3 {
        font-weight: 700;
        font-size: 20px;
        line-height: 24px;
        letter-spacing: 2px;
        margin-bottom: 8px;
      }

      p {
        font-size: 16px;
        line-height: 16px;
        letter-spacing: 2px;
      }
    }

    .txt_box {
      position: relative;

      img {
        width: 12%;
        display: block;
        margin: 0 auto;
      }

      p {
        font-size: 16px;
        line-height: 30px;
        letter-spacing: 2px;
        color: $main_3;

        strong {
          font-weight: 700;
          color: $main_7;
        }
      }
    }
  }
}

@media screen and (min-width:1024px) {
  #quote_box {
    .wrapper {
      @include flex();
      align-items: center;
      justify-content: space-between;
      padding: 83px 101px;

      .img_box {
        width: 40%;

        img {
          margin: 0 auto 39px;
        }
      }

      .txt_box {
        width: 60%;

        p {
          font-size: 22px;
          line-height: 48px;
        }
      }
    }
  }
}
</style>