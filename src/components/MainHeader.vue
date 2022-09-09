<template>
  <nav class="navbar navbar-light bg-dark">
  <a class="navbar-brand px-5" href="#"><img height="50px" src="https://grafica-facile.com/wp-content/uploads/2022/01/spotify-logo.png" alt="spotify-logo"></a>
    
  <div class="search-bar">

      <select name="Genre" id="genre" v-model="search" @change="$emit('search',search)">
            <option value="Rock">Rock</option>
            <option value="Metal">Metal</option>
            <option value="Jazz">Jazz</option>
            <option value="Pop">Pop</option>

          </select>
    </div>
  
</nav>

 
</template>

<script>
    
export default {
  data() {
        return {
           search:'',
        }
     },
    name: "MainHeader",
    props: {
        msg: String
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    a {
    

      &:hover {
        cursor: pointer;
      }
    }

    select {
      border: 2px solid lime;
      width: 200px;
      margin-right: 100px;
      cursor: pointer;
      border-radius: 5px;
    }



</style>
