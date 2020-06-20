<template>
    <div class="navigation">
        <logo></logo>
        <ul class="navigation-list">
            <li class="navigation-item"><nuxt-link to="/">Polo</nuxt-link></li>
            <li class="navigation-item"> <nuxt-link to="/team">La team</nuxt-link></li>
        </ul>
        <!--<div class="navigation-menu">-->
            <!--<span></span>-->
            <!--<span></span>-->
            <!--<span></span>-->
        <!--</div>-->

        <div class="menu">
            <span class="menu-circle"></span>
            <a href="#" class="menu-link">
    <span class="menu-icon">
      <span class="menu-line menu-line-1"></span>
      <span class="menu-line menu-line-2"></span>
      <span class="menu-line menu-line-3"></span>
    </span>
            </a>
        </div>

        <div class="menu-overlay">
            <ul>
                <li class="menu-overlay--item"><nuxt-link to="/">Polo</nuxt-link></li>
                <li class="menu-overlay--item"> <nuxt-link to="/team">La team</nuxt-link></li>
            </ul>
        </div>

    </div>
</template>

<script>
    import Logo from '~/components/Logo/Logo.vue'
    import {gsap, TimelineMax} from 'gsap'
    export default {
        name: "Navigation",
        components: {
            Logo
        },

        mounted(){
            let menulink = document.querySelector('.menu-link')
            let menu = document.querySelector('.menu')
            let overlay = document.querySelector('.menu-overlay')
            let html = document.querySelector('html')
            let menuItemsLink = document.querySelectorAll('.menu-overlay--item a')


            gsap.set(html,{overflow:"scroll"})


            menulink.addEventListener('click',()=>{
                var classes = menu.classList;

                var result = classes.toggle("open");
                if(result) {


                    let tl = new TimelineMax()

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
                            gsap.set(html,{overflow:"scroll"})
                            gsap.set(overlay,{opacity:1,display:'none'});
                        }
                    })


                }
            })

        }
    }
</script>
