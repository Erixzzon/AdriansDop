<template>
  <div id="app" class="container-fluid">
    <Start></Start>
  </div>
</template>

<script>
import Start from './components/Start.vue'

export default {
  name: 'app',
  components: {
    Start
  }
}
</script>

<style>
html, body, #app {
  margin:0;
  padding: 0;
  background-color: #b3b3b3;
  font-family: 'Cormorant Upright', serif;
}

/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
</style>
