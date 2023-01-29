<template>
    <section id="carousel_box" :class="`bg${currentSlide + 1}`">
        <div class="wrapper">
            <!-- 數字 -->
            <div class="num_box">
                <span>0{{ currentSlide + 1 }}</span>
                <span></span>
                <span>04</span>
            </div>
            <!-- 輪播 -->
            <div class="carousel_item_box">
                <CarouselItem v-for="(project, index) in projects" :key="project.id" :currentSlide="currentSlide"
                    :index="index" :direction="direction" :project="project"/>
            </div>
            <!-- 按鈕 -->
            <div class="ctr_box">
                <button @click="toLeft">
                    <img src="../assets/img/left.png" alt="left">
                </button>
                <button @click="toRight">
                    <img src="../assets/img/right.png" alt="right">
                </button>
            </div>
        </div>
    </section>
</template>
<script>
import CarouselItem from '@/components/carousel/CarouselItem.vue'
import { PROJECTS } from "@/assets/js/common.js";
export default {
    name: 'MyCarousel',
    components: { CarouselItem },
    data() {
        return {
            projects: PROJECTS,
            currentSlide: 0,
            sliderInterval: null,
            direction: "right",
        }
    },
    methods: {
        setCurrentSlide(index) {
            this.currentSlide = index;
        },
        toLeft() {
            const index = this.currentSlide > 0 ? this.currentSlide - 1 : this.projects.length - 1;
            this.setCurrentSlide(index);
            this.direction = "left"
            this.startSlideTimer();
        },
        _toRight(){
            const index = this.currentSlide < this.projects.length - 1 ? this.currentSlide + 1 : 0;
            this.setCurrentSlide(index);
            this.direction = "right"
        },
        toRight() {
            this._toRight();
            this.startSlideTimer();
        },
        startSlideTimer(){
            this.stopSlideTimer();
            this.sliderInterval = setInterval(()=>{
                this._toRight();
            },3000)
        },
        stopSlideTimer(){
            clearInterval(this.sliderInterval)
        }
    },
    mounted() {
        this.startSlideTimer();
    },
    beforeUnmount(){
        this.stopSlideTimer();
    }
}
</script>
<style lang="scss" scoped>
$bgLinearGradient: linear-gradient(0deg, rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75));

#carousel_box {
    height: 600px;
    position: relative;
    width: 100%;
    overflow: hidden;
    border-radius: 0 0 50px 50px;
    z-index: 8;
    &::after {
        @include pseudo();
        @include bgImage(bottom);
        z-index: -1;
        filter: blur(10px);
    }

    .wrapper {
        @include maxWidth();
    }
}

@for $i from 1 to 5 {
    #carousel_box.bg#{$i} {

        &::after {
            background-image: $bgLinearGradient, url('../assets/img/project#{$i}_bg.png');
        }
    }
}

.num_box {
    color: $main_3;
    font-weight: 600;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 2.22222px;
    width: 54px;
    height: 54px;
    position: absolute;
    top: 10px;
    right: 10px;

    span {
        position: absolute;

        &:nth-child(1) {
            top: 0;
            left: 0;
        }

        &:nth-child(2) {
            //line
            height: 1px;
            width: 105%;
            background-color: $main_5;
            display: block;
            transform: rotate(-45deg);
            top: 50%;
        }

        &:nth-child(3) {
            bottom: 0;
            right: 0;
        }
    }
}

.ctr_box {
    @include center();
    @include flex();
    @include maxWidth();
    width: 90%;
    justify-content: space-between;

    button {
        background-color: transparent;
        border: none;
    }

    img {
        cursor: pointer;
        width: 30px;
        transition: 0.4s;

        &:hover {
            transform: scale(0.9);
            transition: 0.4s;
        }
    }
}

// 768以上
@media screen and (min-width:768px) {
    #carousel_box {
        height: 700px;
    }
}

// 1024以上
@media screen and (min-width:1024px) {
    #carousel_box {
        height: 550px;

        .ctr_box {
            width: 100%;
            padding: 0 10px;

            img {
                width: 40px;
            }
        }
    }
}

// 1200平板以上
@media screen and (min-width:1200px) {
    #carousel_box {
        height: 986px;

        .wrapper {
            height: 100%;
            position: relative;
        }

        .num_box {
            top: 20%;
            right: 10%;
        }

        .ctr_box {
            width: 100%;
            padding: 0 10px;

            img {
                width: 56px;
            }
        }
    }
}
</style>