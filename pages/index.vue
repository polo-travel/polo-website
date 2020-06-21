<template>
  <div class="container indexContainer">
    <home ></home>
    <teaser ></teaser>
    <feature ></feature>
    <app-footer></app-footer>

  </div>
</template>

<script>
import Home from '~/components/Home/Home.vue'
import Teaser from '~/components/Video/Video.vue'
import Feature from '~/components/Features/Feature.vue'
import AppFooter from '~/components/Footer/Footer.vue'
import { gsap } from 'gsap'


export default {
  components: {
    Home,
    Teaser,
    Feature,
    AppFooter
  },
  created() {
    console.log("created index")
  },
 beforeMount() {
   let content = document.querySelector(".home-content")

   // gsap.to(content,2,{opacity:0,y:22})
   //
   // console.log(content);
 },
 mounted() {


   console.log("ekip")
 }
}
</script>
