<template>
  <div id="app">
    <Header/>
    <Home/>
    <!-- <Footer/> -->
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Header,
    Home,
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
