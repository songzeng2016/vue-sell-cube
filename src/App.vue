<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
  import VHeader from 'components/v-header/v-header'
  import {getSeller} from 'api'

  export default {
    name: 'app',
    components: {
      VHeader
    },
    data() {
      return {
        seller: {}
      }
    },
    created() {
      this._getSeller()
    },
    methods: {
      _getSeller() {
        getSeller().then(seller => {
          this.seller = seller
        })
      }
    },
  }
</script>
<style lang="stylus" scoped>
  #app
    .tab-wrapper
      position: fixed
      top: 136px
      left: 0
      right: 0
      bottom: 0
</style>
