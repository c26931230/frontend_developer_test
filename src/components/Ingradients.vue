<template>
  <!-- OUR INGRADIENTS -->
  <section id="ingradients">
    <div class="wrapper">
      <IngradientsTitle />
      <div class="ingradients_box">
        <IngradientsItem v-for="ingradient in ingradients" :key="ingradient.id" :ingradient="ingradient"
          data-aos="fade-up" data-aos-duration="1500" />
      </div>
        <button class="btn_line" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-50">
          VIEW MORE DIGISALAD’S INGRADIENTS
        </button>
    </div>
  </section>
</template>
<script>
import { INGRADIENTS } from "@/assets/js/common.js";
import IngradientsTitle from '@/components/ingradients/IngradientstTitle.vue'
import IngradientsItem from '@/components/ingradients/IngradientsItem.vue'
export default {
  name: 'Ingradients',
  components: { IngradientsTitle, IngradientsItem },
  data() {
    return {
      ingradients: INGRADIENTS,
    }
  },

}
</script>
<style lang="scss" scoped>
// === ingradients ===
#ingradients {
  background-color: $main_5;
  border-radius: 50px 0 50px 0;
  padding-top: 250px;
  padding-bottom: 400px;
}

.wrapper {
  @include maxWidth();
  width: 90%;
  margin: 0 auto;
}

.ingradients_box {
  @include flex();
  justify-content: space-between;
  color: $main_3;
}


.btn_line {
  border: none;
  width: fit-content;
  margin: 0 auto;
  padding: 10px 20px;
  font-weight: 700;
  font-size: 12px;
  line-height: 22px;
  letter-spacing: 2px;
  color: $main_3;
  display: block;
  position: relative;
  text-align: center;
  background: transparent;
  outline: none;
  cursor: pointer;
  transition: 0.4s;
  text-decoration-line: underline;
  text-decoration-thickness: 3px;
  text-decoration-color: $main_7;
  text-underline-offset: 1px;
  &:hover{
    text-decoration-color: $main_3;
    color: $main_7;
  }

  &::selection {
    background-color: $main_3;
    color: $main_4;
  }
}



@media screen and (min-width:768px) {
  #ingradients {
    padding-bottom: 300px;
  }

  .wrapper {
    width: 80%;
  }

 
  .btn_line {
    text-decoration: none;
    font-size: 18px;
    line-height: 22px;
    letter-spacing: 2px;
    color: $main_3;
    position: relative;
    z-index: 2;
    transition: 0.4s;
    opacity: 1;
    &:hover{
      color: $main_3;
    }
    &::after {
      @include pseudo(100%, 10px, 0, 50%);
      background-color: $main_7;
      z-index: -1;
      transition: 0.4s;
      border: none;
    }

    &:hover::after {
      height: 0px;
      width: 0%;
    }



    &::selection {
      background-color: $main_3;
      color: $main_4;
    }
  }
}

@media screen and (min-width:1024px) {
  #ingradients {
    padding-top: 150px;
    padding-bottom: 380px;
  }
  .wrapper{
    width: 1007px;
  }
  .ingradients_box {
    margin-bottom: 50px;
  }
}

@media screen and (min-width:1200px) {
  .wrapper {
    width: 1135px;
  }
}
</style>