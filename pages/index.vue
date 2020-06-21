<template>
  <div  class="container">
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



export default {
  components: {
    Home,
    Teaser,
    Feature,
    AppFooter
  },
}
</script>
