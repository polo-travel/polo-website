<template>
    <div class="container">
        <div class="team">
            <navigation></navigation>
            <div class="contentWrapper">
                <h1 class="team-title">La team Polo</h1>
                <p class="team-description">Nous sommes 4 étudiants en Bachelor Design Interactif à l’Ecole des Gobelins d’Annecy. <br>
                    Nous avons réalisé ce projet dans le cadre de notre projet de fin d’année sur le thème de la mobilité connectée.</p>
                <div class="membersWrapper">
                    <div class="team-user">
                        <img src="../../static/img/killian.svg" alt="">
                        <span class="team-user--name">Killian Sowa</span>
                        <span class="team-user--role">Développeur</span>
                    </div>
                    <div class="team-user">
                        <img src="../../static/img/lea.svg" alt="">
                        <span class="team-user--name">Léa Pradel</span>
                        <span class="team-user--role">Designer</span>
                    </div>
                    <div class="team-user">
                        <img src="../../static/img/melanie.svg" alt="">
                        <span class="team-user--name">Mélanie Dalla-Vecchia</span>
                        <span class="team-user--role">Designer</span>
                    </div>
                    <div class="team-user">
                        <img src="../../static/img/nael.svg" alt="">
                        <span class="team-user--name">Naël Messaoudene</span>
                        <span class="team-user--role">Développeur</span>
                    </div>

                    <img class="team-dashed" src="../../static/img/dashed-line.svg" alt="">

                </div>
                <img class="team-compass" src="../../static/img/compass.svg" alt="">
            </div>
        </div>
        <app-footer class="footer-team"></app-footer>
    </div>


</template>

<script>
    import Navigation from '~/components/Navigation/Navigation.vue'
    import appFooter from '~/components/Footer/Footer.vue'

    export default {
        name: "index.vue",
        components:{
            Navigation,
            appFooter
        }
    }
</script>

<style scoped>

</style>
