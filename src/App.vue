<template>
  <MyHeader/>
  <router-view/>
 
</template>
<script>
import MyHeader from '@/components/MyHeader.vue'
export default {
  name: 'HomeView',
  components: {
    MyHeader
  }
}
</script>
<style lang="scss">
@import "@/assets/sass/main.scss";
</style>
