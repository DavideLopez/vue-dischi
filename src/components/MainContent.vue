<template>
    <div class="hello bg-secondary">

        {{ listAlbum }}
        
    </div>
  </template>
  
  <script>
   import axios from "axios"

  export default {
    name: 'MainContent',
    props: {
      msg: String
    },
    data() {
        return {
            listAlbum: []
        }
    },
    created() {
        axios
          .get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((res) =>{
            // console.log(res.data)
            this.listAlbum = res.data;
          })
          .catch((err) =>{
            console.log("error", err)
          })
          .finally(() =>{
            // console.log("finito")
          });
    },
  };
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
  
  </style>