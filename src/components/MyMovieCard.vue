<template>
    <section  class="flip-card">
        <div  class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="movie.poster_path != null" class="movieImg" :src="'https://image.tmdb.org/t/p/w342' + movie.poster_path" alt="">
                <img v-else class="notFoundImg" src="../assets/images/image-not-found.png" alt="image not found">
            </div>

            <div class="flip-card-back">
                <div>Titolo: {{movie.title}}</div>
                <div>Titolo originale: {{movie.original_title}}</div> 
                <div v-if="getFlag(movie.original_language) == ''" >Lingua: {{movie.original_language}}</div>
                <img class="flagImg" v-else :src="getFlag(movie.original_language)" alt="flag image">
                <div>
                    <i v-for="n in 5" :key="n" class="fa-star" :class="(n > movie.vote_average)?'fa-regular':'fa-solid'"></i>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'MyMovieCard',
    props: {
        movie: Object
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

<style scoped lang="scss">
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
            width: 100%;
            height: 100%;

            .flip-card-front, .flip-card-back {
                position: absolute;
                width: 100%;
                height: 100%;
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