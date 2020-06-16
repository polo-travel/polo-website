<template>
    <div class="feature">
        <rounded title="Une expérience à offrir
ou à s’offrir" imgUrl="app-travel.svg" description="Faites le plus incroyable des cadeaux et offrez à vos proches
une aventure pleine de surprises et d’activités insolites."></rounded>

        <basic title="Un itinéraire étonnant" imgUrl="app-destination.svg" description="Découvrez vos activités surprises tout au long de votre voyage
en suivant les indications de Polo qui sera votre guide."></basic>

        <rounded title="Une expérience à offrir
ou à s’offrir" imgUrl="app-travel.svg" description="Faites le plus incroyable des cadeaux et offrez à vos proches
une aventure pleine de surprises et d’activités insolites."></rounded>

    </div>
</template>

<script>

    import rounded from '~/components/Features/roundedFeature.vue'
    import basic from '~/components/Features/defaultFeature.vue'

    export default {
        name: "Feature",
        components:{
            rounded,
            basic
        }
    }
</script>

<style scoped>

</style>
