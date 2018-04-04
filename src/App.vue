<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss" scoped>
  @import 'assets/css/main.scss';
  @import '../node_modules/the-grid-flexbox/css/the-grid.min.css';
</style>
