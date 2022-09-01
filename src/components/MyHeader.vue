<template>
    <header>
        <div class="left-header">
            <img src="../assets/images/logo.jpeg" alt="logo image">
            <h3>BOOLFLIX</h3>
        </div>
        <div class="right-header">
            <input type="text" placeholder="Cerca.." id="search" v-model="searchText" />
            <button @click="$emit('search', searchText)">CERCA</button>
        </div>
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
        max-height: 100px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #001434;
        img {
            height: 80px;
            vertical-align: middle;
        }
        h3 {
            display: inline-block;
            color: #fff;
            vertical-align: middle;
        }
        .right-header {
            margin-right: 20px;
            input {
                margin-right: 10px;
                padding: 5px 10px;
                border-radius: 5px;
                border: none;
            }
            button {
                padding: 5px 10px;
                border-radius: 5px;
                border: none;
                background-color: #fff;
                color: #001434;
                &:hover {
                background-color: #00E166;
                color: #fff;
                }
            }

        }

    }
</style>