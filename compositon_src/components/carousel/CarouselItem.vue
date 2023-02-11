<template>
    <transition :name="transitionName">
        <div class="item" v-show="currentSlide === index">
            <div class="img_box">
                <img :src="require(`@/assets/img/${project.image}`)" :alt="project.name">
                <button class="btn">
                    <span>View PROJECT</span>
                    <span class="line">—————</span>
                </button>
            </div>
            <div class="txt_box">
                <h4>HIGHLIGHTED SHOWCASE</h4>
                <h3>{{ project.name }}</h3>
                <p>{{ project.content }}</p>
            </div>
        </div>
    </transition>
</template>
<script>
import {computed,toRef } from 'vue'
export default {
    props: ["project", "currentSlide", "index", "direction"],
    setup(props){
        let direction = toRef(props,'direction')
        let transitionName = computed(()=>{
                return direction.value === "right" ? "slideToRight" : "slideToLeft"
            })
        return{transitionName,direction}
    }
}

</script>
<style lang="scss" scoped>
// 430以下
.item {
    @include flex();
    flex-direction: column;
    padding: 10px 0;
    margin: 0 auto;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}

.img_box {
    width: 100%;
    position: relative;
    padding: 30px;

    img {
        width: 70%;
        display: block;
        margin: 0 auto 30px;
    }

    .btn {
        @include btnRectangle('large');
    }
}

.txt_box {
    width: 100%;
    padding-top: 54px;
    text-align: center;
    order: -1;
    max-height: 300px;

    h4 {
        font-weight: 700;
        font-size: 12px;
        line-height: 19px;
        letter-spacing: 2.22222px;
        color: $main_3;
        margin-bottom: 5px;
    }

    h3 {
        font-weight: 700;
        font-size: 18px;
        line-height: 34px;
        letter-spacing: 3.63636px;
        position: relative;
        width: fit-content;
        margin: 0 auto 20px;
        color: $main_3;
        display: block;
        z-index: 3;

        &::after {
            content: "";
            height: 3px;
            background-color: $main_5;
            position: absolute;
            display: block;
            width: 104%;
            left: -2%;
            bottom: 8px;
            z-index: -1;
        }

        &::before {
            @include decoBall(-15px);
        }
    }

    p {
        display: none;
    }
}

//430以上
@media screen and (min-width:430px) {
    .img_box {
        width: 300px;
        padding: 0px;
        margin: 0 auto;

        img {
            width: 100%;
        }
    }
}


// 768以上
@media screen and (min-width:768px) {
    .item {
        @include maxWidth();
        flex-direction: row;
        align-items: center;
        overflow: hidden;
        .img_box {
            width: 100%;
            padding: 0 30px 0 60px;

            img {
                margin-bottom: 0;
                width: 40%;
            }

            .btn {
                position: absolute;
                bottom: -10px;
                right: 130px;
            }
        }

        .txt_box {
            width: 100%;
            order: 1;
            padding: 0 30px;

            h3 {
                margin-bottom: 10px;
            }

            p {
                @include text();
                display: block;
                color: $main_3;
            }
        }

    }
}
// 1024以上
@media screen and (min-width:1024px) {
    .item {
        @include maxWidth();
        flex-direction: row;
        align-items: center;
        overflow: hidden;
        width: 90%;
        .img_box {
            width: 40%;
            padding: 0 30px 0 60px;

            img {
                margin-bottom: 0;
                width: 100%;
            }

            .btn {
                position: absolute;
                bottom: -5%;
                right: -5%;
            }
        }

        .txt_box {
            width: 60%;
            order: 1;
            text-align: left;
            padding: 0 60px 0 30px;
            h3 {
                margin-left: 0;
            }

            p {
                display: block;
                color: $main_3;
                @include text();
            }
        }

    }
}
// 1200以上
@media screen and (min-width:1200px) {
    .item {
        .img_box {
            width: 540px;

            .btn {
                bottom: -100px;
            }
        }

        .txt_box {
            width: calc(100% - 540px);

            h3 {
                font-size: 32px;
                &::after{
                    height: 6px;
                    bottom: 5px;
                }
                &::before{
                    right: -30px;
                }
            }
            h4{
                font-size: 16px;
            }
        }

    }
}
</style>