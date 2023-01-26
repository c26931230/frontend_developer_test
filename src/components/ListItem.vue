<template>
    <li class="list_item">
        <div class="img_box">
            <img :src="require(`@/assets/img/${imgUrl}.png`)" :alt="imgAlt">
        </div>
        <div class="txt_box">
            <p class="content">{{ content }}</p>
            <p class="title">{{ title }}</p>
        </div>
    </li>
</template>
<script>

export default {
    name: 'ListItem',
    props: {
        content: String,
        title: String,
        imgUrl: String,
        imgAlt: String,
    },
    data() {
        return {
        }
    },
    methods: {

    },
    mounted() {
    },

}
</script>
<style lang="scss" scoped>
// .list {
//     display: block;
//     width: 90%;
//     margin: 0 auto;
//     // height: 100%;
//     border-radius: 30px;
//     overflow: hidden;
//     background-color: #26C6D0;
//     margin-bottom: 20px;

//     .list_item {
//         position: relative;
//         padding: 20px;
//         display: flex;
//         flex-wrap: wrap;
//         align-items: center;
//         justify-content: space-evenly;
//         mix-blend-mode: normal;
//         // z-index: 12;
//         width: 100%;
//         height: 100%;

//         &:after {
//             content: "";
//             background-size: cover;
//             background: url(../assets/img/about_bg.png) center no-repeat;
//             opacity: 0.08;
//             width: 100%;
//             height: 100%;
//             position: absolute;
//             top: 0;
//             left: 0;
//             z-index: 10;
//         }

//         .img_box {
//             width: 10%;
//             border: 1px solid red;

//             img {
//                 width: 100%;
//             }
//         }

//         .txt_box {
//             width: 70%;
//             border: 1px solid red;

//             p {
//                 color: $main_3;
//                 border: 1px solid red;

//                 &:nth-child(1) {
//                     font-size: 16px;
//                     line-height: 19px;
//                     letter-spacing: 1.8px;
//                     margin-bottom: 9px;
//                 }
//             }

//             .title {
//                 font-weight: 700;
//                 font-size: 32px;
//                 line-height: 39px;
//                 letter-spacing: 3.63636px;
//             }
//         }
//     }
// }
</style>