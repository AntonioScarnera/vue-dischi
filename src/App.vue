<template>
  <div id="app">
    <header-comp />
    <main>
      <grid-comp />
    </main>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import GridComp from './components/GridComp.vue'
export default {
  name: 'App',
  components: {
    HeaderComp,
    GridComp
  }
}
</script>

<style lang="scss">
@import './assets/styles/general.scss';

</style>
