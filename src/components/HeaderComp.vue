<template>
  <nav>
    <img src="../assets/images/spotify-logo.png" alt="">
  </nav> 
</template>

<script>
export default {
  name: 'HeaderComp',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../assets/styles/general.scss';

nav{
  width: 100%;
  background-color: $bg-gray;
  img{
    margin: 10px;
    width: 40px;
  }
}
</style>
