<template>
    <div id="app">
        <ItemAppender v-on:add-item="aggregateItem"/>
        <Points v-bind:list="list" v-on:del-item="scrapItem"/>
    </div>
</template>

<script>

import Points from '../components/Todos';
import ItemAppender from '../components/AddTodoItem';
import axios from 'axios'; // #3


export default {
    name: 'Home',
    components: {
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
            axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`) // #14
            .then( response => this.list = this.list.filter( item => item.id !== id)) // #15
            .catch(err => console.log(err));// #6
        },
        aggregateItem( brandNewItem ) {
            const { title, completed } = brandNewItem;// #8
            axios.post('https://jsonplaceholder.typicode.com/todos', {// #13
                title, // #10
                completed // #11
            })// #9
            .then( response => this.list = [...this.list, response.data]) // #12
            .catch(err => console.log(err));// #6
            
        }
    }, 
    created() { // #2
        axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10') // #4
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
