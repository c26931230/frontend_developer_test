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
.main_box{
  margin-top: -200px;
}
.main_box2 {
  margin-top: -350px;
}
//1024以上
@media screen and (min-width:1024px) {
  .main_box {
    margin-top: -100px;
  }
  .main_box2 {
    margin-top: -300px;
  }
}

</style>