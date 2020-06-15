<template>

    <div class="squad">
        <span>{{title}}</span>
        <img :src="require(`../../static/img/${imgUrl}`)" height="130" width="130" alt="">
    </div>

</template>

<script>
    export default {
        name: "roundedFeature",
        props: {
            title: String,
            imgUrl: String,

        }
    }
</script>

<style scoped>

</style>
