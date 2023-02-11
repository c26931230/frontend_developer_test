<template>
    <div class="item">
        <img :src="require(`@/assets/img/${ingradient.image}`)" :alt="ingradient.title">
        <div class="name">
          <h4>{{ ingradient.name }}</h4>
        </div>
        <p>
            Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis
            tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare.
        </p>
        <button>VIEW MORE</button>
    </div>
</template>
<script>
export default {
    props: ["ingradient"],
}
</script>
<style lang="scss" scoped>
 .item {
      @include flex();
      flex-direction: column;
      align-items: center;
      justify-content: space-evenly;
      width: 100%;
      position: relative;
      padding: 30px 25px;

      img {
        display: block;
        width: 30%;
        margin-bottom: 20px;
      }
      .name{
        height: 49px;
        width: 70%;
        position: relative;
        margin-bottom: 20px;
      }
      h4 {
        @include center();
        text-align: center;
        font-weight: 700;
        font-size: 20px;
        line-height: 24px;
        letter-spacing: 2px;
        text-transform: uppercase;
        width: 100%;
        &::selection {
          background-color: $main_3 ;
          color: $main_4;
        }
      }

      p {
        text-align: center;
        @include text();
        margin-bottom: 20px;

        &::selection {
          background-color: $main_3 ;
          color: $main_4;
        }
      }

      button {
        display: block;
        outline: none;
        background-color: transparent;
        padding: 15px 25px;
        color: $main_3;
        border-radius: 30px;
        font-weight: 700;
        font-size: 14px;
        letter-spacing: 2.22px;
        cursor: pointer;
        border: 2px solid $main_3;
        position: relative;
        overflow: hidden;
        transition: 0.4s transform ease-in-out;

        &::after {
          @include pseudo();
          background-color: $main_3;
          border-radius: 30px;
          transform: translate(-100%, 0) rotate(10deg);
          transform-origin: top left;
          transition: 0.4s transform ease-out;
          z-index: -1;
        }

        &:hover::after {
          transform: translate(0, 0);
        }

        &:hover {
          border: 2px solid transparent;
          color: $main_5;
          transform: scale(0.98);
        }

        &::selection {
          background-color: $main_3 ;
          color: $main_4;
        }
      }
    }
    @media screen and (min-width:768px) {
        .item {
          width: 48%;

          button {
            padding: 20px 35px;
          }
        }
    }
    @media screen and (min-width:1024px) {
        .item {
          width: 33.33%;
        }
    }
</style>