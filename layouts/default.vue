<template>
  <!--<div  >-->
    <nuxt  />
  <!--</div>-->
</template>

<script>

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
    },

    mounted() {
      this.lmS = new this.locomotiveScroll({
        el: document.querySelector(".js-scroll"),
        smooth: true,
        scrollbarClass: "c-scrollbar"
      });
      console.log("lmS", this.lmS);

      // window.addEventListener("resize", function(){ this.lmS.update(); });

      console.log(window.innerHeight)
      let layout = document.querySelector("#__layout");

      let scrollContainer = document.querySelector(".js-scroll");
      //html.style.height = ''+scrollContainer.getBoundingClientRect().height +'px'



    }
  }
</script>
