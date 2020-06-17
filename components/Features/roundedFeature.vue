<template>

    <div class="roundedFeature">

        <div class="roundedFeature-content">
            <h2 class="roundedFeature-content--title">{{title}}</h2>
            <p class="roundedFeature-content--description">{{description}}</p>
        </div>

        <div class="roundedFeature-image">
            <img :src="require(`../../static/img/${imgUrl}`)"  alt="">
        </div>
        <img class="roundedFeature-pointsGroup" src="../../static/img/points-group.svg" alt="">


        <div class="bgshape">

            <svg  data-ekip="eeee" xmlns="http://www.w3.org/2000/svg" width="100%" height="100%" viewBox="0 0 1643 361" preserveAspectRatio='none'>
                <g id="Groupe_44" data-name="Groupe 44" transform="translate(82 -1960)">
                    <ellipse id="Ellipse_120" data-name="Ellipse 120" cx="521.5" cy="145" rx="521.5" ry="145" transform="translate(-82 2031)" fill="#19384f"/>
                    <ellipse id="Ellipse_121" data-name="Ellipse 121" cx="325.5" cy="145" rx="325.5" ry="145" transform="translate(910 1960)" fill="#19384f"/>
                </g>
            </svg>




        </div>

        <div class="ooooo" v-if="display == false">
            <h1> ekip</h1>
        </div>

    </div>

</template>

<script>
    export default {
        name: "roundedFeature",
        props: {
            title: String,
            imgUrl: String,
            description: String,
            display:Boolean

        }
    }
</script>

