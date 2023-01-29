<template>
  <div class="title_box">
    <h3 data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">&nbsp;OUR INGRADIENTS&nbsp;&nbsp;</h3>
    <p data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">
      Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
      tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc
      eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante,
      eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis.
      Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras
      lobortis molestie faucibus.
    </p>
    <button class="btn" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200">
      <span>OUR SERVICES</span>
      <span class="line">—————</span>
    </button>
  </div>
</template>

<style lang="scss" scoped>
.title_box {
  margin-bottom: 85px;
  margin-top: 100px;

  h3 {
    @include decoWavy($main_3, $main_6);
    margin-bottom: 45px;
    &::selection {
      background-color: $main_3 ;
      color: $main_4;
    }
  }

  p {
    @include text();
    text-align: center;
    color: $main_3;
    margin: 0 auto 45px;

    &::selection {
      background-color: $main_3 ;
      color: $main_4;
    }

  }

  .btn {
    @include btnRectangle('normal', $main_6, $main_3, $main_3, $main_6);
  }
}
@media screen and (min-width:1024px) {
  .title_box{
    p{
      width: 1007px;
    }
  }
}
</style>