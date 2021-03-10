<template>
  <div class="hello">
    <span v-if="moviesList.length == 0">Loading...</span>
    <div v-if="moviesList.length > 0">
      <ul>
        <li v-for="movie in moviesList" :key="movie.id">
          <a href="#" @click="selectMovie(movie.id)">{{ movie.title }} ({{ movie.original_title }})</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: 'MoviesList',
  props: {
    selectMovie: Function
  },
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
