<template>
    <div id="app">
        <Shapka />
        <Points v-bind:list="list" v-on:del-item="scrapItem"/>
    </div>
</template>

<script>

import Shapka from './components/layout/Header';
import Points from './components/Todos';

export default {
    name: 'app',
    components: {
        Shapka,
        Points
    },
    data() {
        return {
            list: [
                {
                    id: 1,
                    title: "Todo One",
                    completed: false
                },
                {
                    id: 2,
                    title: "Todo Two",
                    completed: false
                },
                {
                    id: 3,
                    title: "Todo Three",
                    completed: false
                }
            ]
        }
    },
    methods: {
        scrapItem( id ) {
            this.list = this.list.filter( item => item.id !== id);
        }
    }
}
</script>

<style>
    body {
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
</style>
