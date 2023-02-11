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
    <MyCarousel />
  </div>
</template>

<script>
import { onMounted,ref } from 'vue'
import { useStore } from 'vuex'
import BannerVideo from '@/components/BannerVideo.vue'
import About from '@/components/About.vue'
import Awards from '@/components/Awards.vue'
import Ingradients from '@/components/Ingradients.vue'
import Quote from '@/components/Quote.vue'
import Experience from '@/components/Experience.vue'
import MyCarousel from '@/components/MyCarousel.vue'
export default {
  name: 'Home',
  components: { BannerVideo, About, Awards, Ingradients, Quote, Experience, MyCarousel },
  setup() {
    // ===store===
    const store = useStore()
    // ref
    const main_box = ref(null) 
    // navbar
    function windowScroll() {
      let scrollHeight = window.scrollY;
      if (scrollHeight >= 20) {
        store.state.isActive = true;
      }
      else {
        store.state.isActive = false;
      }
    }
    // 換背景
    function changeBg() {
      if (main_box.value) {
        let mainBoxTop = main_box.value.offsetTop;
        if (window.scrollY >= mainBoxTop * 1.2) {
        document.body.style.backgroundColor = '#FFF';
      } else {
        document.body.style.backgroundColor = '#F5F5F5';
      }
      }
    }
    onMounted(() => {
      window.addEventListener('scroll', function(){
        windowScroll()
        changeBg()
      })
      windowScroll()
      changeBg()
    })
    return {
      windowScroll,
      changeBg,
      main_box,
    }
  }


}
</script>
<style scoped lang="scss">
.main_box {
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