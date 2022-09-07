<template>
  <nav class="navbar navbar-light bg-dark">
  <a class="navbar-brand" href="#"><img height="50px" src="https://grafica-facile.com/wp-content/uploads/2022/01/spotify-logo.png" alt="spotify-logo"></a>
</nav>
</template>

<script>
export default {
  name: 'MainHeader',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    a {
      padding-left: 50px;
    }

</style>
