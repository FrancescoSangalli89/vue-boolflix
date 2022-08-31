<template>
    <section>
        <li >
            <span>{{movie.title}} - </span>
            <span>{{movie.original_title}} - </span> 
            <span v-if="getFlag(movie.original_language) == ''" >{{movie.original_language}} - </span>
            <img v-else :src="getFlag(movie.original_language)" alt=""> -
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
    img {
        height: 20px;
    }
</style>