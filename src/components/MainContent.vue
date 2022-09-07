<template>
    <div class="hello bg-secondary">
       <div v-for="(poster, i) in listAlbums" :key="i"> 
           IO SONO IL CONTENUTO
          {{poster.i}}
       </div>
        
    </div>
  </template>
  
  <script>
   import axios from "axios";

  export default {
    name: 'MainContent',
    props: {
      msg: String,
    },
    data() {
      return {
        poster: [],
        listAlbums: [],
        title: [],
        author: [],
        genre: [],

      }
      },
    
    created() {
        axios
          .get("https://flynn.boolean.careers/exercises/api/array/music")
          .then((res) => {
            console.log(res.data);
            this.listAlbums = res.data;
          })
          .catch((err) => {
            console.log("error", err);
          })
          .finally(() => {
            // console.log("finito");
          });
          
    }
  }
         
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  
</style>