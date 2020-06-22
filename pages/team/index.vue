<template>
    <div class="container teamContainer js-scroll" data-scroll-container>
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
    import {gsap, TimelineMax} from "gsap"

    export default {
        name: "index.vue",
        components:{
            Navigation,
            appFooter
        },
        mounted() {

            let el;
            if($nuxt.$route.path === "/team/"){
                el = document.querySelector(".teamContainer")
            }else{
                console.log("else")
            }
            let _that = this
            this.lmS = new this.locomotiveScroll({
                el: el,
                smooth: true,
                smoothMobile: true,
                scrollbarClass: "c-scrollbar"
            });

            console.log("lmS", this.lmS);



            this.lmS.update()

            // window.addEventListener("resize", function(){ this.lmS.update(); });


            console.log(window.innerHeight)
            let layout = document.querySelector("#__layout");
            let scrollContainer = document.querySelector(".js-scroll");
            let container = document.querySelectorAll(".container");
            console.log("killu")
            // scrollContainer.style.height = ''+scrollContainer.getBoundingClientRect().height +'px'

            // scroll event
            // this.lmS.on('scroll', func => {

            // setTimeout(function () {
            //   this.lmS.update()
            //   console.log("zzzzz")
            // },5000000)

            // });


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
        watch: {
            '$route.path': function() {
                console.log($nuxt.$route.path)

                this.lmS.destroy()

            }
        },
    }
</script>

<style scoped>

</style>
