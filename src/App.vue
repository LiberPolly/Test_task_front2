<template>
  <div id="app">
    <Catalogue/>
  </div>
</template>

<script>
import Catalogue from './components/Catalogue.vue'

export default {
  name: 'App',
  components: {
    Catalogue
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
</style>
