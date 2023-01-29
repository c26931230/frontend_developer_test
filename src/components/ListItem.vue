<template>
    <li class="list_item">
        <div class="img_box">
            <img :src="require(`../assets/img/${imgUrl}.png`)" :alt="imgAlt">
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
}
</script>
