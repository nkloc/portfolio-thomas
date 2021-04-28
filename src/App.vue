<template>
  <div id="app">
    <div id="nav">
      <Header/>
      <router-view/>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="stylus">
@import 'css/main'

#app
  font-family $font-content
  font-size 16px
  line-height 24px
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale

</style>