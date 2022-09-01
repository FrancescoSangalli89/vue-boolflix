<template>
    <header>
        <input type="text" placeholder="Cerca.." id="search" v-model="searchText" />
        <button @click="$emit('search', searchText)">Cerca</button>
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
    header {
        input {
            margin: 10px 20px;
        }
    }
</style>