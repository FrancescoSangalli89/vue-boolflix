<template>
    <main>
        <ul>
            <h2 v-if="movieList.length !== 0">Movies</h2>
            <MyMovieCard v-for="(movie, index) in movieList" :key="index" :movie="movie" />
        </ul>
        <ul>
            <h2 v-if="serieList.length !== 0">Series</h2>
            <MyTvCard v-for="(serie, index) in serieList" :key="index" :serie="serie" />
        </ul>
    </main>
</template>

<script>

import MyMovieCard from './MyMovieCard.vue';
import MyTvCard from './MyTvCard.vue';

export default {
    name: 'MyMain',
    components: {
        MyMovieCard,
        MyTvCard
    },
    props: {
        movieList: Array,
        serieList: Array
    }
}
</script>

<style lang="scss">

</style>