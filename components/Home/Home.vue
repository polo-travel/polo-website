<template>
    <div class="home">
        <navigation></navigation>

        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="1366" height="1059" viewBox="0 0 1366 1059">
            <defs>
                <clipPath id="clip-path">
                    <rect id="Rectangle_176" data-name="Rectangle 176" width="1366" height="1059" fill="#fff"/>
                </clipPath>
                <linearGradient id="linear-gradient" x1="0.5" x2="0.5" y2="0.727" gradientUnits="objectBoundingBox">
                    <stop offset="0" stop-color="#d31c21"/>
                    <stop offset="1" stop-color="#e64526"/>
                </linearGradient>
                <linearGradient id="linear-gradient-2" y1="0.5" x2="1" y2="0.5" gradientUnits="objectBoundingBox">
                    <stop offset="0" stop-color="#a3d9ed"/>
                    <stop offset="0.419" stop-color="#d1eaf3"/>
                    <stop offset="1" stop-color="#d2ebf3"/>
                </linearGradient>
                <filter id="Tracé_81" x="-65.666" y="-235.979" width="1640.834" height="1207.369" filterUnits="userSpaceOnUse">
                    <feOffset input="SourceAlpha"/>
                    <feGaussianBlur stdDeviation="49.5" result="blur"/>
                    <feFlood flood-opacity="0.161"/>
                    <feComposite operator="in" in2="blur"/>
                    <feComposite in="SourceGraphic"/>
                </filter>
            </defs>
            <g id="Groupe_de_masques_1" data-name="Groupe de masques 1" clip-path="url(#clip-path)">
                <ellipse id="Ellipse_59" data-name="Ellipse 59" cx="594.65" cy="487.65" rx="594.65" ry="487.65" transform="translate(-380.97 -152.41)" fill="url(#linear-gradient)"/>
                <g transform="matrix(1, 0, 0, 1, 0, 0)" filter="url(#Tracé_81)">
                    <path id="Tracé_81-2" data-name="Tracé 81" d="M173.4,330.23C107.956,384.471-1.874,475.563,45.75,557.325c42.272,72.766,166.585,64.406,267.626,165.8,83.022,83.4,41.879,132.224,133.838,180.244,88.374,46.048,208.17,43.974,249.313,43.239,212.687-3.712,442.41-101.224,492.636-223.483,54.841-133.561-147.29-192.216-79.095-317.183,63.482-116.105,276.365-135.835,267.626-219.9-7.708-73.87-178.663-121.824-194.619-126.137C862.522-27.248,398.411,143.633,173.4,330.23Z" transform="translate(48.71 -123.97)" fill="url(#linear-gradient-2)"/>
                </g>
            </g>
        </svg>

        <h1 class="title">
            polo website
        </h1>
        <h2 class="subtitle">
            polo !!!!!! thewebsite
        </h2>
    </div>
</template>

<script>
    import Navigation from '~/components/Navigation/Navigation.vue'

    export default {
        name: "Home",
        components: {
            Navigation
        }
    }
</script>
