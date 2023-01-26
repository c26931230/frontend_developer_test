<template>
    <section id="experience_box">
      <div class="wrapper">
        <h3 data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-300">&nbsp;OUR BRAND EXPERIENCE&nbsp;&nbsp;</h3>
        <p data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-300">Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
          tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu
          tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
          eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam
          consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis
          molestie faucibus.</p>
        <img src="../assets/img/ClientList.png" alt="DigiSalad Client List" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-300">
      </div>
    </section>
</template>
<script>
export default {
    name: 'Experience',
    data() {
        return {
        }
    },
    methods:{
    },
    mounted() {
    },

}
</script>
<style lang="scss" scoped>

#experience_box {
    @include maxWidth();
    margin-top: 30px;
    .wrapper {
      width: 100%;
      margin: 0 auto;
      // padding: 0 10px;

      h3 {
        // @include h3('#OUR BRAND EXPERIENCE#', $main_4, $main_5);
        @include decoWavy();
        margin-bottom: 58px;
      }

      p {
        @include text(24px);
        color: $main_4;
        text-align: center;
        margin-bottom: 36px;
        padding: 0 10px;
      }

      img {
        width: 100%;
        padding: 0 10px;
      }
    }
}
@media screen and (min-width:500px) {
  #experience_box{
    margin-top: 50px;
  }
}
@media screen and (min-width:700px) {
  #experience_box{
    margin-top: 70px;
    .wrapper{
      width: 80%;
    }
  }
}
</style>