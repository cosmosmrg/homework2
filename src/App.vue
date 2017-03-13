<template>
  <div id="app">
    <iccs340-left-sidenav></iccs340-left-sidenav>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
    Iccs340LeftSidenav: require('./LeftSidenav')
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
