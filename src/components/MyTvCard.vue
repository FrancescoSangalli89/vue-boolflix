<template>
    <section>
        <li >
            <span>{{serie.name}} - </span>
            <span>{{serie.original_name}} - </span> 
            <span v-if="getFlag(serie.original_language) == ''" >{{serie.original_language}} </span>
            <img v-else :src="getFlag(serie.original_language)" alt=""> -
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

<style>

</style>