<template>
  <div id="app">
    <MyHeader @search="searching" />
    <MyMain :movieList="movieList" :serieList="serieList" />
  </div>
</template>

<script>

import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      movieList: [],
      serieList: [],
      apiUrl: 'https://api.themoviedb.org/3',
      apiKey: 'af6fbe18e93f8959cb08c13e609cab58',
      language: 'it-IT'
    }
  },
  methods: {
    searching(searchText) {
      axios.get(this.apiUrl + '/search/movie?api_key=' + this.apiKey + '&language=' + this.language + '&query=' + searchText)
      .then(res => {
        this.movieList = res.data.results;
        this.movieList.forEach(movie => {
          movie.vote_average = Math.ceil(movie.vote_average / 2);
        });
      })
      .catch(err => {
        console.log(err);
      })
      axios.get(this.apiUrl + '/search/tv?api_key=' + this.apiKey + '&language=' + this.language + '&query=' + searchText)
      .then(res => {
        this.serieList = res.data.results;
        this.serieList.forEach(serie => {
          serie.vote_average = Math.ceil(serie.vote_average / 2);
        });
      })
      .catch(err => {
        console.log(err);
      })

    }
  }
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.css';
@import './styles/general.scss';
</style>
