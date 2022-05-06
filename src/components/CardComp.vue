<template>
  <div class="text-center card-container mt-5">
      <img :src="item.poster" :alt="item.title">
      <h6 class="mt-3 fw-bold">{{item.title}}</h6>
      <div class="autore">{{item.author}}</div>
      <div class="anno">{{item.year}}</div>
  </div>
</template>

<script>
export default {
    name: 'CardComp',
        props:{
        item: Object
    }
}
</script>

<style lang="scss">
  @import "../assets/styles/vars.scss";
  .card-container{

    background-color: $bg-gray;
    height: 100%;
    h6{
        text-transform: uppercase;
    }
    img{
        width: 80%;
        margin: 10px auto;
    }
    .autore{
      font-size: 14px;
      color: grey;
    }
    .anno{
      font-size: 12px;
      color: grey;
    }
  }
</style>