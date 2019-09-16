<template>
    <div id="app">
        <Shapka />
        <ItemAppender v-on:add-item="aggregateItem"/>
        <Points v-bind:list="list" v-on:del-item="scrapItem"/>
    </div>
</template>

<script>

import Shapka from './components/layout/Header';
import Points from './components/Todos';
import ItemAppender from './components/AddTodoItem';
import axios from 'axios'; // #3


export default {
    name: 'app',
    components: {
        Shapka,
        Points,
        ItemAppender
    },
    data() {
        return {
            list: []
        }
    },
    methods: {
        scrapItem( id ) {
            this.list = this.list.filter( item => item.id !== id);
        },
        aggregateItem( brandNewItem ) {
            this.list = [...this.list, brandNewItem];
        }
    }, 
    created() { // #2
        axios.get('https://jsonplaceholder.typicode.com/todos') // #4
        .then( response => this.list = response.data) // #5
        .catch(err => console.log(err));// #6
    }
}
</script>

<style>
    body {
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
    .btn:hover {
        background: #666;
    }
</style>
