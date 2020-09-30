<template>
  <amazghmap msg="Map of Historically Amazigh Villages in Tunisia"/>
</template>

<script>
import amazghmap from './components/amazghmap.vue'

export default {
  name: 'App',
  components: {
    amazghmap
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
