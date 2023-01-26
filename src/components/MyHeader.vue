<template>
    <header id="header" ref="header" v-show="$store.state.isMenuOpen == false">
        <div class="holder" ref="holder" :style="{
            backgroundColor: $store.state.isActive ? '#ffffff90' : 'transparent'
        }">
            <div class="wrapper">
                <a href="#" class="logo">
                    <img src="@/assets/img/logo_blue.png" alt="digisalad logo" v-show="$store.state.isActive == true">
                </a>
                <div class="function_box">
                    <a href="#" class="btn_1">START YOUR PROJECT</a>
                    <div class="toggle" @click="openMenu">
                        <span v-for="i in 3" :style="{
                            backgroundColor: $store.state.isActive ? '#585880' : 'white'
                        }"></span>
                    </div>
                </div>
            </div>

        </div>
    </header>
    <MyMenu/>
</template>

<script>
// import ListItem from '@/components/ListItem.vue'
import MyMenu from '@/components/MyMenu.vue'
export default {
    name: 'MyHeader',
    components: {MyMenu},
    data() {
        return {
            isActive: false,
        }
    },
    methods:{
        openMenu(){
            this.$store.state.isMenuOpen = true
            console.log(this.$store.state.isMenuOpen);
        }
    },
    mounted() {
    },

}
</script>

<style scoped lang="scss">
@import "@/assets/sass/header.scss";


</style>
