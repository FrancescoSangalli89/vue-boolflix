<template>
    <section>
        <li >
            {{serie.name}} - 
            {{serie.original_name}} - 
            {{serie.original_language}} - 
            {{serie.vote_average}}
        </li>
    </section>
</template>

<script>
export default {
    name: 'MyTvCard',
    props: {
        serie: Object
    }
}
</script>

<style>

</style>