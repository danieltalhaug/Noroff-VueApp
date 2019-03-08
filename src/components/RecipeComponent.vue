<template v-for="recipe in recipes" >
 <div class="card">
    <img :src="recipes.results[0].thumbnail">
    <h2>{{recipes.results[0].title}}</h2>
    <p>{{recipes.results[0].ingredients}}</p>
    <a :href="recipes.results[0].href">Check it out</a>
 </div>
</template>

<script>
export default {
  name: 'RecipePuppy',
  data() {
    return {
      recipes: []
    }
  },
  beforeMount: function() {
    const app = this;
    const conversionUrl = 'https://cors-anywhere.herokuapp.com/';
    const recipePuppyUrl = 'http://www.recipepuppy.com/api/';

    fetch(conversionUrl + recipePuppyUrl)
    .then(function(response) {
      return response.json();
    })
    .then(function(result) {
      app.recipes = result;
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card {
  background-color: #eee;
  padding: 50px 0 50px 0;
  margin: 5px;
}
.card a {
  color: #c20000;
}
</style>
