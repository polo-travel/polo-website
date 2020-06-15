<template>
  <div class="container">
    <home></home>
    <teaser></teaser>
    <feature></feature>

  </div>
</template>

<script>
import Home from '~/components/Home/Home.vue'
import Teaser from '~/components/Video/Video.vue'
import Feature from '~/components/Features/Feature.vue'

export default {
  components: {
    Home,
    Teaser,
    Feature
  }
}
</script>
