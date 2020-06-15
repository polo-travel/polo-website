<template>
  <div class="container">
    <home></home>
    <teaser></teaser>
  </div>
</template>

<script>
import Home from '~/components/Home/Home.vue'
import Teaser from '~/components/Video/Video.vue'

export default {
  components: {
    Home,
    Teaser
  }
}
</script>
