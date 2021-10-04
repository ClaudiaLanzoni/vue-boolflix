<template>
  <div id="app">
    <Header @searching='search'/>
    <Main :pellicole="movies" :tvSeries="serieTv"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    
  },

  data : function () {
    return {
      apiMovie : 'https://api.themoviedb.org/3/search/movie',
      apiSeries : 'https://api.themoviedb.org/3/search/tv',
      apiKey : 'cb11640258dfdce63e5b0a147809a751',
      movies : [],
      serieTv : []
     
    }
  },

  methods: {
    search : function (needle) {
      axios.get (this.apiMovie, {
        params : {
          api_key : this.apiKey,
          query : needle,
          language : 'it-IT'
        }
      }).then(
        (risposta) => {
          this.movies = [...risposta.data.results]
        })

        axios.get (this.apiSeries, {
        params : {
          api_key : this.apiKey,
          query : needle,
          language : 'it-IT'
        }
      }).then(
        (risposta) => {
          this.serieTv = [...risposta.data.results]
        })
    }
    }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
