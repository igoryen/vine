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


export default {
    name: 'app',
    components: {
        Shapka,
        Points,
        ItemAppender
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
        },
        aggregateItem( brandNewItem ) {
            this.list = [...this.list, brandNewItem];
        }
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
