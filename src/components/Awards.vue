<template>
  <section id="award_box">
    <div class="wrapper">
      <div class="txt_box">
        <h3 data-aos="fade-up" data-aos-duration="1500" data-aos-offset="300">&nbsp;AWARDS&nbsp;&nbsp;</h3>
        <p data-aos="fade-up" data-aos-duration="1500" data-aos-offset="300">Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras
          ullamcorper bibendum bibendum. Duis
          tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
          eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. </p>
      </div>
      <div class="img_box">
        <img src="../assets/img/awards.png" alt="Asia Smart App Awards" v-for="i in 4" data-aos="fade-up"
          data-aos-duration="1500" data-aos-offset="300">
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: 'Awards',
}
</script>
<style lang="scss" scoped>
// === award_box ===
#award_box {
  @include maxWidth();
  position: relative;
  transform: translateY(50%);
  margin-bottom: 50px;

  .wrapper {
    width: 90%;
    margin-left: auto;
    background-color: $main_3;
    padding: 30px;
    border-radius: 50px 0 50px 50px;
  }
}

.txt_box {
  h3 {
    @include decoWavy();
  }

  p {
    @include text();
    margin-top: 45px;
    color: $main_4;
    text-align: center;
  }
}

.img_box {
  position: relative;
  padding: 30px 0;

  img {
    width: 50%;
    padding-right: 10px;
    padding-bottom: 10px;
    vertical-align: top;
  }
}

@media screen and (min-width:768px) {
  #award_box {
    .wrapper {
      margin-left: auto;
    }
  }

  .img_box {
    img {
      max-width: 360px;
    }
  }
}

@media screen and (min-width:1024px) {
  #award_box {

    .wrapper {
      @include flex();
      width: 95%;
      padding: 65px 0 65px 58px;
      align-items: center;

    }
  }
  .txt_box {
        width: 40%;
        padding-right: 19px;
        h3{
          margin: 0 auto 0 0;
        }
        p{
          text-align: left;
        }
      }

      .img_box {
        width: 60%;

        img {
          max-width: 283px;
          padding: 9.5px 18px;
        }
      }
}

</style>