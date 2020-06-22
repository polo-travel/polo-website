<template>
    <div class="navigation">
        <logo></logo>
        <ul class="navigation-list">
            <li class="navigation-item"><nuxt-link to="/">Polo</nuxt-link></li>
            <li class="navigation-item"> <nuxt-link to="/team">La team</nuxt-link></li>
        </ul>

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
    export default {
        name: "Navigation",
        components: {
            Logo
        },

        mounted(){



        }
    }
</script>
