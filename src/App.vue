<template>
  <div id="app">
    <div class="row">
      <div class="col-md-12">
        <h1>Git bisect test</h1>
        <img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/ca/Studio_Ghibli_logo.svg/440px-Studio_Ghibli_logo.svg.png">
      </div>
    </div>
    <br>
    <div class="row">
      <div class="col-md-6">
        <MoviesList/>
      </div>
      <div class="col-md-6">
        asdsad
      </div>
    </div>
  </div>
</template>

<script>
import MoviesList from './components/MoviesList.vue'

export default {
  name: 'App',
  components: {
    MoviesList
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
