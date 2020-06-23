<template>
    <div class="feature">
        <rounded title="Une expérience à offrir
ou à s’offrir" imgUrl="app-travel.svg" description="Faites le plus incroyable des cadeaux et offrez à vos proches
une aventure pleine de surprises et d’activités insolites." :display=false></rounded>

        <basic title="Un itinéraire étonnant" imgUrl="app-destination.svg" description="Découvrez vos activités surprises tout au long de votre voyage
en suivant les indications de Polo qui sera votre guide." bgImg="destination.svg" ></basic>

        <rounded title="Une aventure personnalisée" imgUrl="app-travel.svg" description="Grâce à un questionnaire simplifié, Polo vous crée un voyage insolite
adapté à votre profil d’aventurier." v-bind:class="{ red: isActive}" :display=true ></rounded>

        <basic title="Un itinéraire étonnant" imgUrl="app-polowers.png" description="Découvrez vos activités surprises tout au long de votre voyage
en suivant les indications de Polo qui sera votre guide." bgImg="polowers.svg" v-bind:class="{ basic: isActive}" ></basic>


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
        },
        data: function () {
          return{
              isActive: true,
          }
        }
    }
</script>

<style scoped>

</style>
