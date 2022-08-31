<template>
    <main>
        <ul>
            <h2>Movies</h2>
            <MyMovieCard v-for="(movie, index) in movieList" :key="index" :movie="movie" />
        </ul>
        <ul>
            <h2>Series</h2>
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
    },
    data() {
        return {
            
        }
    }
}
</script>

<style lang="scss">

</style>