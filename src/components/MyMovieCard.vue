<template>
    <section>
        <li >
            {{movie.title}} - 
            {{movie.original_title}} - 
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
    }
}
</script>

<style>

</style>