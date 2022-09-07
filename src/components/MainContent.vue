<template>
    <div class="hello bg-secondary">
        io sono il contenuto
    </div>
  </template>
  
  <script>
   import axios from "axios"

  export default {
    name: 'MainContent',
    props: {
      msg: String
    },
    created() {
        axios
          .get('https://flynn.boolean.careers/exercises/api/array/music')
          
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
  
  </style>