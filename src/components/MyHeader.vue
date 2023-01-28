<template>
    <header id="header" ref="header" v-show="$store.state.isMenuOpen == false">
        <div class="holder" ref="holder" :style="{
            backgroundColor: $store.state.isActive ? '#ffffff90' : 'transparent'
        }">
            <div class="wrapper">
                <router-link to="/" class="logo">
                    <img src="@/assets/img/logo_blue.png" alt="digisalad logo" v-show="$store.state.isActive == true">
                </router-link>
                <div class="function_box">
                    <button class="btn_1">START YOUR PROJECT</button>
                    <div class="toggle" @click="openMenu">
                        <span v-for="i in 3" :style="{
                            backgroundColor: $store.state.isActive ? '#585880' : 'white'
                        }"></span>
                    </div>
                </div>
            </div>

        </div>
    </header>
    <MyMenu />
</template>

<script>
import MyMenu from '@/components/MyMenu.vue'
export default {
    name: 'MyHeader',
    components: { MyMenu },
    data() {
        return {
            isActive: false,
        }
    },
    methods: {
        openMenu() {
            this.$store.state.isMenuOpen = true
        }
    },
    mounted() {
    },

}
</script>

<style scoped lang="scss">
#header {
    overflow: hidden;

    .holder {
        position: fixed;
        top: 0;
        z-index: 10;
        min-width: 100%;

        .wrapper {
            @include maxWidth;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            padding: 15px 10px;

            .logo {
                width: 100px;
                position: relative;
                display: block;

                img {
                    width: 100%;
                    vertical-align: top;
                }
            }

            .function_box {
                display: flex;
                flex-wrap: wrap;
                align-items: center;

                .btn_1 {
                    display: block;
                    padding: 12px 10px;
                    width: fit-content;
                    background: linear-gradient(90deg, $main_1 3.94%, $main_2 94.73%);
                    border-radius: 24px;
                    cursor: pointer;
                    color: $main_3;
                    margin-right: 30px;
                    font-size: 14px;
                    border: none;
                    position: relative;
                    overflow: hidden;
                    transition: 0.4s transform ease-in-out;

                    &::after {
                        background-color: #fff;
                        border-radius: 30px;
                        content: '';
                        display: block;
                        height: 100%;
                        width: 100%;
                        position: absolute;
                        left: 0;
                        top: 0;
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
                }

                .toggle {
                    width: 30px;
                    height: 22px;
                    display: flex;
                    flex-wrap: wrap;
                    flex-direction: column;
                    justify-content: space-between;
                    cursor: pointer;

                    span {
                        width: 100%;
                        height: 3px;
                        background-color: $main_3;
                        display: block;
                        border-radius: 5px;

                        &:nth-child(3) {
                            width: 80%;
                            margin-left: auto;
                        }
                    }
                }
            }
        }

    }
}
</style>
