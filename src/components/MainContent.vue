<template>
  <div class="container"> 
    <CardDischi v-for="(disco,i) in filteredAlbums" :key="i" 
      :poster="disco.poster"
      :title="disco.title"
      :author="disco.author"
      :genre="disco.genre"
      :year="disco.year"
    />
  </div>
</template>

<script>
import axios from 'axios';
import CardDischi from './CardDischi.vue';

export default {
    name: "MainComponent",
    props: {
      search: {
        type: String,
        default:'',
      }
    },
    data() {
        return {
            ListAlbum: [],
        };
    },
    computed: {
      filteredAlbums() {
        return this.ListAlbum.filter((el) => {
          const genre = el.genre;
          const find = this.search;

          if(genre.includes(find)) {
            return true;
          }

          return false;
        }) 
      }
    },
    created() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
            this.ListAlbum = res.data.response;
            console.log(res.data);
        });
    },
    components: { 
      CardDischi 
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .container {
    display: grid;
    grid-template-columns: repeat(5,5fr);
    gap: 25px;
    max-width: 1000px;
  }

</style>