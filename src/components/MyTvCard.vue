<template>
    <section>
        <li >
            <img v-if="serie.poster_path != null" class="serieImg" :src="'https://image.tmdb.org/t/p/w342' + serie.poster_path" alt="">
            <img v-else class="serieImg" src="../assets/images/image-not-found.png" alt="image not found">
            <span>{{serie.name}} - </span>
            <span>{{serie.original_name}} - </span> 
            <span v-if="getFlag(serie.original_language) == ''" >{{serie.original_language}} </span>
            <img class="flagImg" v-else :src="getFlag(serie.original_language)" alt="flag image"> -
            <span>{{serie.vote_average}}</span>
        </li>
    </section>
</template>

<script>
export default {
    name: 'MyTvCard',
    props: {
        serie: Object
    },
    methods: {
        getFlag(lang){
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
        .serieImg {
            height: 100px;
            width: 80px;
        }
        .flagImg {
            height: 20px;
        }
    }
</style>