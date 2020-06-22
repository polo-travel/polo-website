<template>
  <!--<div  >-->
    <nuxt  />
  <!--</div>-->
</template>

<script>
  import {gsap, TimelineMax} from 'gsap'

  export default {
    data() {
      return {
        lmS: null
      };
    },
    beforeMount(){
      let layout = document.querySelector("#__layout");
      layout.classList.add("js-scroll")
      layout.dataset.scrollContainer = ""

      window.onbeforeunload = function () { window.scrollTo(0,0); };


    },
    mounted() {
      window.onbeforeunload = function () { window.scrollTo(0,0); };

    }



    }
</script>
