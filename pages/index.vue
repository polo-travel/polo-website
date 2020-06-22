<template>
  <div class="container indexContainer js-scroll" data-scroll-container>
    <home ></home>
    <teaser></teaser>
    <feature ></feature>
    <app-footer></app-footer>

  </div>
</template>

<script>
import Home from '~/components/Home/Home.vue'
import Teaser from '~/components/Video/Video.vue'
import Feature from '~/components/Features/Feature.vue'
import AppFooter from '~/components/Footer/Footer.vue'
import { gsap, TimelineMax } from 'gsap'


export default {
  components: {
    Home,
    Teaser,
    Feature,
    AppFooter
  },
  data() {
    return {
      lmS: {
        class: ''
      }
    };
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

    let el;
    if($nuxt.$route.path === "/"){
      console.log(" mounted == ///")
      el = document.querySelector(".indexContainer")
    }else if($nuxt.$route.path === "/team"){
      el = document.querySelector(".teamContainer")
    }else{
      console.log("else")
    }
    let _that = this

    this.$nextTick(function () {

      this.lmS = new this.locomotiveScroll({
        el: el,
        smooth: true,
        smoothMobile: true,
        scrollbarClass: "c-scrollbar"
      })
      this.lmS.update()
      this.lmS.on('call', this.handler)
      }.bind(this));


    console.log("lmS", this.lmS);


    console.log(window.innerHeight)
    let layout = document.querySelector("#__layout");
    let scrollContainer = document.querySelector(".js-scroll");
    let container = document.querySelectorAll(".container");
    console.log("killu")
    // scrollContainer.style.height = ''+scrollContainer.getBoundingClientRect().height +'px'

    // scroll event call EVENT




    /** Navigation **/
    let menulink = document.querySelector('.menu-link')
    let menu = document.querySelector('.menu')
    let overlay = document.querySelector('.menu-overlay')
    let html = document.querySelector('html')
    let menuItemsLink = document.querySelectorAll('.menu-overlay--item')
    //

    console.log($nuxt.$route);

    menuItemsLink.forEach( (it)=>{
      console.log(it)
      it.addEventListener("click",()=>{
        _that.lmS.destroy()
        _that.lmS.init()

      })
    });

    // menuItemsLink.addEventListener('click',()=>{
    //   // _that.lmS.destroy()
    //   // _that.lmS.init()
    //
    //   console.log("clickkk")
    //
    // })

    menulink.addEventListener('click',()=>{
      var classes = menu.classList;

      var result = classes.toggle("open");
      if(result) {

        let tl = new TimelineMax()

        _that.lmS.stop()

        tl.set(".c-scrollbar",{display:"none"});
        tl.set(".menu-circle",{transform:"scale(60)"});
        tl.set(overlay,{opacity:1,display:'flex'});
        tl.set(menuItemsLink,{translateY:"100%"})
        gsap.set(html,{overflow:"hidden"})

        tl.fromTo(menuItemsLink,1,{opacity:0},{delay:0.3,translateY:"0%",stagger: {each: 0.2},display:"block", opacity:1, ease: "power2.out"})


      } else {
        gsap.set(".menu-circle",{transform:"scale(60)"});
        gsap.to(menuItemsLink,1,{
          stagger: {each: 0.1},
          translateY:"100%",
          ease: "power2.out",
          opacity:0,onComplete: function(){
            gsap.set(".menu-circle",{transform:"scale(2.1)"});
            overlay.classList.remove("open")
            _that.lmS.start()

            gsap.set(".c-scrollbar",{display:"none"});
            gsap.set(html,{overflow:"hidden"})
            gsap.set(overlay,{opacity:1,display:'none'});

          }
        })
      }
    })

  },
  methods: {
    handler(caller) {
      console.log('caller:', caller);
      let [
        func,
        param,
      ] = caller;

      console.log('func', func)
      this[func](param);
    },
    // defaultImage(param){
    //   console.log('hi!',param);
    //   let img = document.querySelectorAll(".defaultFeature-image")
    //   let content = document.querySelectorAll(".defaultFeature-content")
    //
    //   const style = getComputedStyle(img[0])
    //
    //   let op = style.opacity
    //   console.log(op)
    //     if (op == 0){
    //       let tl = new TimelineMax()
    //       tl.fromTo(img[0],1,{opacity:0,translateY:"50"},{opacity:1,translateY:"0"})
    //       tl.fromTo(content[0],1,{opacity:0,translateY:"50"},{opacity:1,translateY:"0"})
    //     }
    //     else {
    //       let tl = new TimelineMax()
    //       gsap.set(img[1],{opacity:0})
    //       gsap.set(content[1],{opacity:0})
    //
    //       tl.fromTo(img[1],1,{opacity:0,translateY:"50"},{opacity:1,translateY:"0"})
    //       tl.fromTo(content[1],1,{opacity:0,translateY:"50"},{opacity:1,translateY:"0"})
    //
    //
    //     }

    // },
    // sayBye(param){
    //   console.log('bye.',param);
    // }
  },
  watch: {
    '$route.path': function() {
      console.log($nuxt.$route.path)

      this.lmS.destroy()

    },
    'lmS.class':{
      handler: function (val, oldVal) {
        console.log(val, oldVal);
      },
      deep: true
    }

  },

}
</script>
