<template>
  <div class="hello">
    <div>
      <span v-if="movie === null">Loading...</span>
      <table class="table" v-if="movie === null">
        <tr>
          <td>id</td>
          <td>{{ movie.id }}</td>
        </tr>
        <tr>
          <td>title</td>
          <td>{{ movie.title }}</td>
        </tr>
        <tr>
          <td>original_title</td>
          <td>{{ movie.original_title }}</td>
        </tr>
        <tr>
          <td>original_title_romanised</td>
          <td>{{ movie.original_title_romanised }}</td>
        </tr>
        <tr>
          <td>description</td>
          <td>{{ movie.description }}</td>
        </tr>
        <tr>
          <td>director</td>
          <td>{{ movie.director }}</td>
        </tr>
        <tr>
          <td>producer</td>
          <td>{{ movie.producer }}</td>
        </tr>
        <tr>
          <td>release_date</td>
          <td>{{ movie.release_date }}</td>
        </tr>
        <tr>
          <td>running_time</td>
          <td>{{ movie.running_time }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: 'MoviesList',
  props: {
    movieId: null,
  },
  data () {
    return {
      movie: null
    }
  },
  mounted () {
    axios
      .get(`https://ghibliapi.herokuapp.com/films/${this.movieId}`)
      .then(response => (this.movie = response.data))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
