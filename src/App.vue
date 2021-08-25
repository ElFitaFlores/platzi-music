<template lang="pug">
  #app
    h1 {{msg}}
    p {{1 + 1}}
    p {{'Hola' + 'mundo'}}
    p {{person.name}}
    p {{person.name.toUpperCase()}}
    p {{JSON.stringify(person)}}
    p {{true ? 'true' : 'false'}}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hola mundo',
      person: {
        name: 'Rafa'
      }
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
