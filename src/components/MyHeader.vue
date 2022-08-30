<template>
    <header>
        <input type="text" placeholder="Cerca film..." id="search" v-model="searchText" />
        <button @click="$emit('movieSearch', searchText)">Cerca</button>
    </header>
</template>

<script>
export default {
    name: 'MyHeader',
    data() {
        return {
            searchText: ''
        }
    }
}
</script>

<style lang="scss">

</style>