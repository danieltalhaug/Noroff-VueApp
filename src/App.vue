<template>
  <div id="app">
    <RecipePuppy/>
  </div>
</template>

<script>

import RecipePuppy from './components/RecipeComponent.vue'

export default {
  name: 'app',
  components: {
    RecipePuppy
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
}
</style>
