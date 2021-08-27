<template lang="pug">
  #app
    input(v-model="name")
    button(@click="format") format
    p {{formatName}}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: '',
      lastName: '',
      formatName: ''
    }
  },
  computed: {
    fullName () {
      return `${this.name} ${this.lastName}`
    }
  },
  watch: {
    name (newVal, oldVal) {
      console.log(newVal, oldVal)
    }
  },
  methods: {
    format () {
      this.formatName = this.name.split(' ').join('-')
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
