<template>
  <div id="js-scroll" >
    <nuxt />
  </div>
</template>

<script>

  export default {
    data() {
      return {
        lmS: null
      };
    },
    mounted() {
      this.lmS = new this.locomotiveScroll({
        el: document.querySelector("#js-scroll"),
        smooth: true
      });
      console.log("lmS", this.lmS);
    }
  }
</script>
