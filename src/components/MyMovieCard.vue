<template>
    <section>
        <li >
            {{movie.title}} - 
            {{movie.original_title}} - 
            <img src="" alt="">
            {{movie.original_language}} - 
            {{movie.vote_average}}
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
            flags: [
                {
                    language: 'en',
                    src: '../assets/images/gb.svg',
                    gotFlag: true
                },
                {
                    language: 'it',
                    src: '../assets/images/it.svg',
                    gotFlag: true
                },
            ],
            gotFlag: false
        }
    },
    computed: {
        getFlag() {
            for (let i = 0; i < this.flags.length; i++) {
                if (this.movie.original_language == en || this.movie.original_language == it) {
                    this.movie.original_language = 
                }
                
            }
        }
    }
}
</script>

<style>

</style>