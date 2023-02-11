<template>
    <transition name="fade">
        <nav id="menu" v-show="$store.state.isMenuOpen == true">
            <div class="wrapper">
                <div class="function_box">
                    <h1><img src="@/assets/img/logo_white.png" alt="digiSalad" class="logo"></h1>
                    <div class="toggle" @click="closeMenu">
                        <span v-for="i in 2"></span>
                    </div>
                </div>

                <ul class="item_box">
                    <!-- 3欄 -->
                    <!-- 左 -->
                    <li class="item">
                        <ul class="list_box">
                            <ListItem imgUrl="about_icon" content="EMPOWERING BRANDS" title="ABOUT US" imgAlt="vegetable" />
                            <ListItem imgUrl="work_icon" content="CASE STUDIES" title="WORKS" imgAlt="tomato" />
                        </ul>
                    </li>
                    <!-- 中 -->
                    <li class="item">
                        <ul class="list_box">
                            <ListItem imgUrl="careers_icon" content="BE COOL WITH US" title="CAREERS" imgAlt="cheese" />
                            <ListItem imgUrl="insight_icon" content="OUR STRATEGIES" title="INSIGHTS" imgAlt="cucumber" />
                        </ul>
                    </li>
                    <!-- 右 -->
                    <li class="item">
                        <ul class="list_box">
                            <ListItem imgUrl="services_icon" content="AREAS OF EXPERTISE" title="SERVICES"
                                imgAlt="carrot" />
                            <li class="list_item">
                                <div class="info_box">
                                    <p class="content">START YOUR JOURNEY WITH US</p>
                                    <p class="title">CONTACT</p>
                                </div>
                            </li>
                        </ul>
                    </li>
                </ul>
            </div>
        </nav>
    </transition>
</template>
<script>
import { useStore } from 'vuex'
import ListItem from '@/components/ListItem.vue'
export default {
    name: 'MyMenu',
    components: { ListItem },
    setup(){
         // ===store===
         const store = useStore()
         function closeMenu(){
            store.state.isMenuOpen = false
         }
        return {closeMenu}
    }
}
</script>
<style lang="scss">
#menu {
    min-height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;
    &::after {
        @include pseudo();
        z-index: -1;
        background: linear-gradient(180deg, $main_6 3.61%, $main_5 95.7%);
        opacity: 0.9;
    }

    .wrapper {
        @include maxWidth();
        max-height: 100vh;
        height: fit-content;
        overflow-y: scroll;

        .function_box {
            //上方
            @include flex();
            align-items: center;
            justify-content: space-between;
            padding: 15px 10px;

            img {
                width: 100px;
                display: block;
            }

            .toggle {
                width: 30px;
                height: 22px;
                position: relative;
                cursor: pointer;
                span {
                    position: absolute;
                    height: 3px;
                    width: 100%;
                    background-color: $main_3;
                    border-radius: 5px;
                    top: 50%;

                    &:nth-child(1) {
                        transform: translateY(-50%) rotate(45deg);
                    }

                    &:nth-child(2) {
                        transform: translateY(-50%) rotate(-45deg);
                    }
                }
            }
        }
    }
}

//ul
.item_box {
    padding: 10px;
}

.list_box {

    //ul
    .list_item {
        //li
        @include flex();
        cursor: pointer;
        align-items: center;
        justify-content: space-between;
        border-radius: 20px;
        width: 100%;
        margin-bottom: 10px;
        padding: 10px;
        height: 120px;
        position: relative;
        overflow: hidden;
        z-index: 5;
        transition: .4s;
        &:hover{
            transform: translateY(-10px);
            transition: .4s;
        }
        &::after {
          @include pseudo();
            z-index: -1;
        }

        &::before {
            @include pseudo();
            z-index: -1;
        }

        .img_box {
            width: 30%;

            img {
                height: 100%;
                margin: 0 auto;
                display: block;
            }
        }

        .txt_box {
            width: 65%;
            color: $main_3;

            .content {
                font-size: 16px;
                line-height: 19px;
                letter-spacing: 1.8px;
                margin-bottom: 9px;
            }

            .title {
                font-weight: 700;
                font-size: 32px;
                line-height: 39px;
                letter-spacing: 3.63636px;
                position: relative;
                width: fit-content;

                &:before {
                    @include decoBall(-20px,50%);
                }
            }
        }
    }
}

//左邊
.item:nth-child(1) {
    .list_box {
        .list_item {
            &:nth-child(1) {

                //about
                &::after {
                    background: url(../assets/img/about_bg.png);
                    opacity: 0.08;
                    @include bgImage();
                }

                &::before {
                    background-color: $main_5;
                }
            }

            &:nth-child(2) {

                //works
                &::after {
                    background: url(../assets/img/works_bg.png);
                    opacity: 0.06;
                    @include bgImage();
                }

                &::before {
                    background-color: rgba(238, 108, 138, 0.8);
                    ;
                }

                .txt_box {
                    .title {
                        &::before {
                            background-color: $main_5;
                        }
                    }
                }
            }
        }
    }

}

// 中間
.item:nth-child(2) {
    .list_box {
        .list_item {
            &:nth-child(1) {

                //careers
                &::after {
                    background: url(../assets/img/careers_bg.png);
                    opacity: 0.1;
                    @include bgImage();
                }

                &::before {
                    background-color: #E6A94E;
                }
            }

            &:nth-child(2) {

                //insight
                &::after {
                    background: url(../assets/img/insight_bg.png);
                    opacity: 0.08;
                    @include bgImage();
                }

                &::before {
                    background-color: $main_2;
                    ;
                }
            }
        }
    }

}

// 右邊
.item:nth-child(3) {
    .list_box {
        .list_item {
            &:nth-child(1) {

                //services
                &::after {
                    background: url(../assets/img/services_bg.png);
                    opacity: 0.1;
                    @include bgImage();
                }

                &::before {
                    background-color: $main_6;
                }
            }

            &:nth-child(2) {
                //contact
                background-color: $main_3;
                .info_box{
                    width: 100%;
                    p {
                        width: 100%;
                        text-align: center;
                    }
    
                    .content {
                        color: $main_4;
                        margin-bottom: 9px;
                    }
    
                    .title {
                        color: $main_5;
                        font-weight: 700;
                        font-size: 32px;
                        line-height: 39px;
                        letter-spacing: 3.63636px;
                        position: relative;
                        width: fit-content;
                        margin: 0 auto;
                        &:before {
                            @include decoBall(-20px,50%);
                        }
                    }
                }
            }
        }
    }

}

// 平板以上
@media screen and (min-width:1024px) {
    #menu{
        .wrapper{
            overflow-y: auto;
        }
    }
    .item_box {
        //ul
        padding: 0;
        @include flex();
        justify-content: space-evenly;
        height: calc(100vh - 85px);
        min-height: 480px;
        width: 90%;
        margin: 0 auto;

        .item {
            padding: 0 20px;
            align-self: center;
            .list_box{
                .list_item{
                    margin-bottom: 0;
                }
            }
        }

        .item:nth-child(1) {
            min-height: 400px;  
            height: 70vh;
            width: 37%;

            .list_box {
                @include flex();
                justify-content: space-between;
                align-items: center;
                flex-direction: column;
                height: 100%;
                .list_item:nth-child(1) {
                    height: calc(40% - 40px);
                    margin-bottom: 40px;
                }

                .list_item:nth-child(2) {
                    height: 60%;
                    padding: 60px 30px;
                    .img_box{
                        align-self: flex-end;
                    }
                    .txt_box{
                        align-self: flex-end;
                    }
                }
            }
        }

        .item:nth-child(2) {
            width: 26%;
            height: calc(100vh - 85px);
            min-height: 480px;
            .list_box {
                height: 100%;
                flex-direction: column;
                align-items: center;
                justify-content: space-between;
                .list_item{
                    flex-direction: column;
                    justify-content: flex-end;
                    align-items: flex-start;
                }
                .list_item:nth-child(1) {
                    height: calc(58% - 40px);
                    margin-bottom: 40px;
                    padding: 0 10px 15% 10px;
                    .img_box{
                        margin-bottom: 28px;
                    }
                    .txt_box{
                        width: 100%;
                    }
                }

                .list_item:nth-child(2) {
                    height: 42%;
                    padding: 0 10px 15% 10px;
                    .img_box{
                        margin-bottom: 15px;
                        width: 10%;
                        img{
                            width: 100%;
                            height: auto;
                        }
                    }
                    .txt_box{
                        width: 100%;
                    }
                }
            }
        }

        .item:nth-child(3) {
            width: 37%;
            height: 70vh;
            min-height: 400px;
            .list_box {
                @include flex();
                flex-direction: column;
                align-items: center;
                justify-content: space-between;
                height: 100%;

                .list_item:nth-child(1) {
                    height: calc(60% - 40px);
                    margin-bottom: 40px;
                    padding: 60px 30px;
                    .img_box{
                        align-self: flex-end;
                    }
                    .txt_box{
                        align-self: flex-end;
                    }
                }

                .list_item:nth-child(2) {
                    height: 40%;
                    padding: 0px 42px;
                    .info_box{
                        .content{
                         text-align: left;
                         margin-bottom: 9px;
                         width: fit-content;
                         flex-grow: 2;
                         height: calc(100% - 50px);
                        }
                        .title{
                         text-align: left;
                         margin: 0;
                         height: fit-content;
                        }
                    }
                }
            }
        }
    }

    .list_box {
        .list_item {
            .img_box {
                width: 20%;

                img {
                    height: 100%;
                    margin: 0 auto;
                    display: block;
                }
            }

            .txt_box {
                width: 80%;
                padding-left: 10px;
                color: $main_3;
            }
        }
    }

}
</style>