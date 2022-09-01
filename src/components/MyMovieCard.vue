<template>
    <section>
        <li >
            <img v-if="movie.poster_path != null" class="movieImg" :src="'https://image.tmdb.org/t/p/w342' + movie.poster_path" alt="">
            <img v-else class="movieImg" src="../assets/images/image-not-found.png" alt="image not found">
            <span>{{movie.title}} - </span>
            <span>{{movie.original_title}} - </span> 
            <span v-if="getFlag(movie.original_language) == ''" >{{movie.original_language}} </span>
            <img class="flagImg" v-else :src="getFlag(movie.original_language)" alt="flag image"> -
            <span>{{movie.vote_average}}</span>
            <i v-for="n in 5" :key="n" class="fa-star" :class="(n > movie.vote_average)?'fa-regular':'fa-solid'"></i>
        </li>
    </section>
</template>

<script>
export default {
    name: 'MyMovieCard',
    props: {
        movie: Object
    },
    data() {
        return {
            stars: []
        }
    },
    methods: {
        getFlag(lang) {
        let flags = ['en', 'it', 'fr', 'ja', 'ko', 'de', 'es'];
        if(flags.includes(lang))
            return require('../assets/images/' + lang + '.svg');
        else
            return '';
        }
    }
}
</script>

<style lang="scss">
    section {
        .movieImg {
            height: 100px;
            width: 80px;
        }
        .flagImg {
            height: 20px;
        }
    }
</style>