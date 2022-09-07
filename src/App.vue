<template>
  <div id="app">
    
    <MainHeader msg="Welcome to Your Vue.js App"/>
    <MainContent />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent
}
}
</script>

<style lang="scss">

</style>
