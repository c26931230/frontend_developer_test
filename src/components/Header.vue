<template>
    <header id="header" ref="header">
        <div class="holder" ref="holder" :style="{
            backgroundColor: $store.state.isActive ? 'white' : 'transparent'
        }">
            <a href="#" class="logo">
                <img src="@/assets/img/logo_blue.png" alt="digisalad logo" v-show="$store.state.isActive == true">
            </a>
            <div class="function_box">
                <a href="#" class="btn_1">START YOUR PROJECT</a>
                <div class="toggle">
                    <span v-for="i in 3" :style="{
                        backgroundColor: $store.state.isActive ? '#585880' : 'white'
                    }"></span>
                </div>
            </div>

        </div>
    </header>
    <nav class="SideMenu">
        <ul>
            <li>
                <a href="#">
                    <div>
                        <p>EMPOWERING BRANDS</p>
                        <p>ABOUT US</p>
                    </div>
                </a>
            </li>
            <!-- <li>ABOUT US</li> -->
            <li>CAREERS</li>
            <li>SERVICES</li>
            <li>WORKS</li>
            <li>INSIGHT</li>
            <li>CONTACT</li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            isActive: false,
        }
    },
    mounted() {
    },

}
</script>

<style scoped lang="scss">
@import "@/assets/sass/header.scss";

//
</style>
