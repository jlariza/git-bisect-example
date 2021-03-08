<template>
  <div class="hello">
    <div>
      <ul>
        <li v-for="movie in moviesList" :key="movie.id">
          <a v-on:click="selectMovie(movie.id)">{{ movie.title }} ({{ movie.original_title }})</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MoviesList',
  props: {
    selectMovie: Function
  }
  data () {
    return {
      moviesList: []
    }
  },
  mounted () {
    axios
      .get('https://ghibliapi.herokuapp.com/films/')
      .then(response => (this.moviesList = response.data))
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
