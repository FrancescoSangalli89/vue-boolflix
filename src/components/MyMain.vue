<template>
    <main class="container cards-list">
        <h2 v-if="movieList.length !== 0">Movies</h2>
        <div>
            <MyCard v-for="(movie, index) in movieList" :key="index" :item="movie" />
        </div>
        <h2 v-if="serieList.length !== 0">Series</h2>
        <div>
            <MyCard v-for="(serie, index) in serieList" :key="index" :item="serie" />
        </div>
    </main>
</template>

<script>

import MyCard from './MyCard.vue';

export default {
    name: 'MyMain',
    components: {
        MyCard
    },
    props: {
        movieList: Array,
        serieList: Array
    }
}
</script>

<style scoped lang="scss">
    .container {
        max-width: 1170px;
        height: 100vh;
        margin: auto;

        div {
            margin: 10px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        h2 {
                margin-top: 2rem;
        }
    }

</style>