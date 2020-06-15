<template>
    <div class="navigation">
        <logo></logo>
        <ul class="navigation-list">
            <li class="navigation-item">Polo</li>
            <li class="navigation-item">La team</li>
            <li class="navigation-item">Contact</li>
        </ul>
    </div>
</template>

<script>
    import Logo from '~/components/Logo/Logo.vue'
    export default {
        name: "Navigation",
        components: {
            Logo
        }
    }
</script>
