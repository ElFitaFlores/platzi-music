<template lang="pug">
#app
  pm-header
  pm-loader(v-show="isLoading")
  section.section(v-show="!isLoading")
    nav.nav.has-shadow
      .container
        input.input.is-large(
          type="text",
          placeholder="Buenas canciones",
          v-model="searchQuery"
        )
        a.button.is-info.is-large(@click="search") Buscar
        a.button.is-danger.is-large &times;

    .container
      p
        small {{ searchMessage }}

    .container.results
      .columns.is-multiline
        .column.is-one-quarter(v-for="t in tracks")
          pm-track(:track="t")

  pm-footer
</template>

<script>
import trackService from './services/track'
import PmFooter from './components/layout/Footer.vue'
import PmHeader from './components/layout/Header.vue'
import PmTrack from '@/components/Track.vue'
import PmLoader from '@/components/shared/Loader.vue'

export default {
  name: 'app',
  data () {
    return {
      searchQuery: '',
      tracks: [],
      isLoading: false
    }
  },
  watch: {
    name (newVal, oldVal) {
      console.log(newVal, oldVal)
    }
  },
  methods: {
    search () {
      if (!this.searchQuery) {
        return
      }

      this.isLoading = true

      trackService.search(this.searchQuery).then((res) => {
        console.log(res)
        this.tracks = res.tracks.items
        this.isLoading = false
      })
    }
  },
  computed: {
    searchMessage () {
      return `Encontrados: ${this.tracks.length}`
    }
  },
  components: { PmFooter, PmHeader, PmTrack, PmLoader }
}
</script>

<style lang="scss">
@import "./scss/main.scss";

.results {
  margin-top: 50px;
}
</style>
