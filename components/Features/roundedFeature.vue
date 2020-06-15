<template>

    <div class="roundedFeature">

        <div class="roundedFeature-content">
            <h2 class="roundedFeature-title">{{title}}</h2>
            <p class="roundedFeature-description">{{description}}</p>
        </div>

        <div class="roundedFeature-image">
            <img :src="require(`../../static/img/${imgUrl}`)"  alt="">
        </div>
        <img class="roundedFeature-pointsGroup" src="../../static/img/points-group.svg" alt="">

    </div>

</template>

<script>
    export default {
        name: "roundedFeature",
        props: {
            title: String,
            imgUrl: String,
            description: String,

        }
    }
</script>

