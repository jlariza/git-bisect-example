<template>
  <div class="hello">
    <div>
      <ul>
        <li>id</li>
        <li>title</li>
        <li>original_title</li>
        <li>original_title_romanised</li>
        <li>description</li>
        <li>director</li>
        <li>producer</li>
        <li>release_date</li>
        <li>running_time</li>
      </ul>
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
