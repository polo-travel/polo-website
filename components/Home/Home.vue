<template>
    <div class="home">
        <h1>Hoome</h1>
        <navigation></navigation>
        <h1 class="title">
            polo website
        </h1>
        <h2 class="subtitle">
            polo !!!!!! thewebsite
        </h2>
    </div>
</template>

<script>
    import Navigation from '~/components/Navigation/Navigation.vue'

    export default {
        name: "Home",
        components: {
            Navigation
        }
    }
</script>
