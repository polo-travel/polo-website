<template>
    <div class="footer">

        <top-footer></top-footer>
        <bottom-footer></bottom-footer>
    </div>
</template>

<script>
    import topFooter from '~/components/Footer/TopFooter.vue'
    import bottomFooter from '~/components/Footer/BottomFooter.vue'

    export default {
        name: "Footer",
        components:{
            topFooter,
            bottomFooter
        },
    }
</script>

<style scoped>

</style>
