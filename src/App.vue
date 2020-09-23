<template>
  <div id="app">
    <img alt="Anime logo" src="https://myanimelist.net/images/mal-logo-xsmall.png" width="500">
    <br />
    <br />
    <anime/>
  </div>
</template>

<script>
import anime from './components/anime.vue'

export default {
  name: 'App',
  components: {
    anime
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
