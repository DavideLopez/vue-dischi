<template>
  <div class="container"> 
    <CardDischi v-for="(disco,i) in ListAlbum" :key="i" 
      :poster="disco.poster"
      :title="disco.title"
      :author="disco.author"
      :year="disco.year"
    />
  </div>
</template>

<script>
import axios from 'axios';
import CardDischi from './CardDischi.vue';

export default {
    name: "MainComponent",
    data() {
        return {
            ListAlbum: [],
        };
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
  
body {
  --bs-body: color #1e2b3d;

  .container {
    display: grid;
    grid-template-columns: repeat(5,1fr);
    gap: 2rem;
    max-width: 850px;
  }
}
</style>