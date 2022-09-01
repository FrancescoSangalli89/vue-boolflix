<template>
    <section  class="flip-card">
        <div  class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="serie.poster_path != null" class="serieImg" :src="'https://image.tmdb.org/t/p/w342' + serie.poster_path" alt="">
                <img v-else class="notFoundImg" src="../assets/images/image-not-found.png" alt="image not found">
            </div>

            <div class="flip-card-back">
                <div>Titolo: {{serie.name}}</div>
                <div>Titolo originale: {{serie.original_name}}</div> 
                <div v-if="getFlag(serie.original_language) == ''" >Lingua: {{serie.original_language}}</div>
                <img class="flagImg" v-else :src="getFlag(serie.original_language)" alt="flag image">
                <div>
                    <i v-for="n in 5" :key="n" class="fa-star" :class="(n > serie.vote_average)?'fa-regular':'fa-solid'"></i>
                </div>
            </div>
        </div>
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
    .flip-card {
        background-color: transparent;
        perspective: 1000px;
        width: 342px;
        height: 513px;
        margin: 10px;
        display: flex;
        justify-content: center;
        
        .flip-card-inner {
            position: relative;
            text-align: center;
            transition: transform 0.8s;
            transform-style: preserve-3d;

            .flip-card-front, .flip-card-back {
                position: absolute;
                backface-visibility: hidden;
            }

            .flip-card-back {
                background-color: #001434;
                color: white;
                transform: rotateY(180deg);
                padding: 20px;

                div, .flagImg {
                    margin-top: 3rem;
                }

                .flagImg {
                    height: 20px;
                }
            }
        }
        &:hover .flip-card-inner {
            transform: rotateY(180deg);
        }
    }
    .flip-card-inner, .flip-card-front, .flip-card-back, .notFoundImg {
        width: 100%;
        height: 100%;
    }
</style>