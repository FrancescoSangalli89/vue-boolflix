<template>
  <div id="app">
    <MyHeader @movieSearch="receivedMovie" />
    <MyMain :searchedMovie="searchedMovie" />
  </div>
</template>

<script>

import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      searchedMovie: ''
    }
  },
  methods: {
    receivedMovie(searchText) {
      this.searchedMovie = searchText;
    }
  }
}
</script>

<style lang="scss">

</style>
