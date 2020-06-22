<template>
    <div class="defaultFeature" >

        <div data-scroll data-scroll-call="defaultImage, green" data-scroll-offset="700" class="defaultFeature-image">
            <img :src="require(`../../static/img/${imgUrl}`)"  alt="">
        </div>

        <div class="defaultFeature-content">
            <h2 class="defaultFeature-content--title">{{title}}</h2>
            <p class="defaultFeature-content--description">{{description}}</p>
        </div>

        <img class="defaultFeature-bg" :src="require(`../../static/img/${bgImg}`)" alt="">
    </div>
</template>

<script>
    export default {
        name: "defaultFeature",
        props: {
            title: String,
            imgUrl: String,
            description: String,
            display: Boolean,
            bgImg: String
        },
    }
</script>

