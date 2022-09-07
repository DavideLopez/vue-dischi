<template class="bg-dark">
    <div class="card">
      <div class="card-content">
        <img :src="poster" alt="">
        <h3 class="album">{{ title }}</h3>
        <div class="info-album">
          <div class="author">{{ author }}</div>
          <div class="year">{{ year }}</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      poster: String,
      title: String,
      author: String,
      year: Number,
    }
  }
  </script>

<style lang="scss" scoped>

.card {
  background-color: #212529;
  padding: 15px;
  border-radius: 0;
  .card-content {
    text-align: center;
    &:hover {
        opacity: 0.2;
    }
    
    .album {
      font-size: 14px;
      color: white;
      text-transform: uppercase;
      padding: 20px 0;
    }
    .info-album {
      color: gray;
      font-size: 16px;
    } 

    .album {
        font-weight: bold;
    }
  }
}
</style>