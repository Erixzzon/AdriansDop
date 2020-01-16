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

</style>
