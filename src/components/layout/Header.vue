<template lang="pug">
    section.hero.is-success
        .hero-head
            header.navbar
            .container
                .nav-start
                    .nav-item
                        strong Platzi Music
                .nav-end.nav-menu

        .hero-body
            .container.has-text-centered
                h1.title Platzi Music
                h2.subtitle Canciones que están Vuenisimas
                pm-player
</template>
<script>
import PmPlayer from '@/components/PLayer.vue'

export default {
  components: { PmPlayer }
}
</script>
