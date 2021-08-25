<template lang="pug">
  #app
    p(v-show="showValue") {{value}}
    p(v-if="showValue") {{value}}
    p(v-else-if="false") {{'algo mas'}}
    p(v-else) {{'lo ultimo'}}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hola mundo',
      showValue: true,
      value: 'Algo'
    }
  }
}
</script>

<style lang="scss">
  @import './scss/main.scss'
</style>
