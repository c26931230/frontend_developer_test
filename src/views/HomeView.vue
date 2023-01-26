<template>
  <BannerVideo/>
  <h1>HI</h1>
  <About/>
  <div class="main_box" :style="{
    transform: `translateY(${-halfAwardBox}px)`
  }" ref="main_box">
    <Awards :receiveAwardHeight="receiveAwardHeight"/>
    <Ingradients :halfAwardBox="halfAwardBox" :halfQuoteBox="halfQuoteBox"/>
    <Quote :receiveQuoteHeight="receiveQuoteHeight"/>
  </div>
  <div class="main_box2" :style="{
    transform: `translateY(${-halfQuoteBox * 1.5}px)`
  }">
    <Experience/>
    <Club/>
  </div>
</template>

<script>
import BannerVideo from '@/components/BannerVideo.vue'
import About from '@/components/About.vue'
import Awards from '@/components/Awards.vue'
import Ingradients from '@/components/Ingradients.vue'
import Quote from '@/components/Quote.vue'
import Experience from '@/components/Experience.vue'
import Club from '@/components/Club.vue'
export default {
  name: 'Home',
  components:{BannerVideo,About,Awards,Ingradients,Quote,Experience,Club},
  data() {
    return {
      halfAwardBox: '',
      halfQuoteBox: '',
    }
  },
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
    receiveAwardHeight(e){
      this.halfAwardBox = e;
    },  
    receiveQuoteHeight(e){
      this.halfQuoteBox = e;
    }, 
    changeBg() {
      let mainBoxTop = this.$refs.main_box.offsetTop;
      if (window.scrollY >= mainBoxTop * 1.2) {
        document.body.style.backgroundColor = '#FFF';
      } else {
        document.body.style.backgroundColor = '#F5F5F5';
      }
    },
    next(e,a) {
      this.x -= 100;
      console.log(e,a);
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
@import "@/assets/sass/home.scss";
</style>