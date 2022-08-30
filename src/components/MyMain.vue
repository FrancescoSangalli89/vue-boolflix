<template>
    <main>
        <div>

        </div>
    </main>
</template>

<script>

    import axios from 'axios';

export default {
    name: 'MyMain',
    props: {
        searchedMovie: String
    },
    data() {
        return {
            movies: [],
            endpoint: `https://api.themoviedb.org/3/search/movie?api_key=af6fbe18e93f8959cb08c13e609cab58&query=2001&language=it-IT`,
        }
    },
    methods: {
        getMovies() {
            if (this.searchedMovie != '') {
                axios.get(this.endpoint)
                .then(response => {
                    console.log(this.endpoint)
                    this.movies.push(response.data.results);
                })
            }
        }
    }
}
</script>

<style>

</style>