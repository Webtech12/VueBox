<template>
  <div id="app">
    <Blogs/>
  </div>
</template>

<script>
import Blogs from './components/Blogs.vue'

export default {
  name: 'app',
  components: {
    Blogs
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
