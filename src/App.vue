<template>
  <MyHeader/>
  <router-view/>
 
</template>
<script>
import MyHeader from '@/components/MyHeader.vue'
export default {
  name: 'APP',
  components: {
    MyHeader
  }
}
</script>
