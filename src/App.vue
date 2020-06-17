<template>
  <div id="app">
    <Loader msg="Arey"/>
  </div>
</template>

<script>
import Loader from './components/Loader.vue'

export default {
  name: 'App',
  components: {
    Loader
  }
}
</script>

<style>
body{
  margin: 0;
  height: 100vh;
}
#app {
  overflow: auto;
  -webkit-overflow-scrolling: auto;
  /* background: #256e1e; */
  background: #2c3e50;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}
</style>
