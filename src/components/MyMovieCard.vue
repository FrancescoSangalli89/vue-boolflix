<template>
    <section>
        <li >
            <img class="movieImg" :src="'https://image.tmdb.org/t/p/w342' + movie.poster_path" alt="">
            <span>{{movie.title}} - </span>
            <span>{{movie.original_title}} - </span> 
            <span v-if="getFlag(movie.original_language) == ''" >{{movie.original_language}} </span>
            <img class="flagImg" :src="getFlag(movie.original_language)" alt="flag image"> -
            <span>{{movie.vote_average}}</span>
        </li>
    </section>
</template>

<script>
export default {
    name: 'MyMovieCard',
    props: {
        movie: Object
    },
    methods: {
        getFlag(lang){
        let flags = ['en', 'it', 'fr', 'ja', 'ko', 'de'];
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
        }
        .flagImg {
            height: 20px;
        }
    }
</style>