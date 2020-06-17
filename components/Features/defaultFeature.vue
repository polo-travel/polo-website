<template>
    <div class="defaultFeature" >

        <div class="defaultFeature-image">
            <img :src="require(`../../static/img/${imgUrl}`)"  alt="">
        </div>

        <div class="defaultFeature-content">
            <h2 class="defaultFeature-content--title">{{title}}</h2>
            <p class="defaultFeature-content--description">{{description}}</p>
        </div>

        <img class="defaultFeature-bg" src="../../static/img/destination.svg" alt="">
    </div>
</template>

<script>
    export default {
        name: "defaultFeature",
        props: {
            title: String,
            imgUrl: String,
            description: String,
            display: Boolean
        },
    }
</script>

