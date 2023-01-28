<template>
  <BannerVideo />
  <About />
  <div class="main_box" ref="main_box">
    <Awards />
    <Ingradients />
    <Quote />
  </div>
  <div class="main_box2">
    <Experience />
    <!-- <Club /> -->
    <MyCarousel/>
  </div>
</template>

<script>
import BannerVideo from '@/components/BannerVideo.vue'
import About from '@/components/About.vue'
import Awards from '@/components/Awards.vue'
import Ingradients from '@/components/Ingradients.vue'
import Quote from '@/components/Quote.vue'
import Experience from '@/components/Experience.vue'
import MyCarousel from '@/components/MyCarousel.vue'
// import Club from '@/components/Club.vue'
export default {
  name: 'Home',
  components: { BannerVideo, About, Awards, Ingradients, Quote, Experience,MyCarousel },
  methods: {
    windowScroll() {
      let scrollHeight = window.scrollY;
      if (scrollHeight >= 20) {
        this.$store.state.isActive = true;
      }
      else {
        this.$store.state.isActive = false;
      }
    },
    changeBg() {
      if (this.$refs.main_box) {
        let mainBoxTop = this.$refs.main_box.offsetTop;
        if (window.scrollY >= mainBoxTop * 1.2) {
        document.body.style.backgroundColor = '#FFF';
      } else {
        document.body.style.backgroundColor = '#F5F5F5';
      }
      }
    },
  },
  mounted() {
    const self = this;
    window.addEventListener("scroll", function () {
      self.windowScroll();
      self.changeBg();
    })
    this.windowScroll();
  },


}
</script>
<style scoped lang="scss">
@import "@/assets/sass/main.scss";

// 手機
.main_box {
  transform: translateY(-200px);
}

//平板橫以上
@media screen and (min-width:1024px) {
  .main_box {
    transform: translateY(-100px);
  }
}

//手機
.main_box2 {
  background-color: $main_3;
  transform: translateY(-500px);
}

//平板橫以上
@media screen and (min-width:1024px) {
  .main_box2 {
    transform: translateY(-400px);
  }
}

</style>