<template>
    <div id="app">
        <Points v-bind:list="list"/>
    </div>
</template>

<script>

import Points from './components/Todos';

export default {
    name: 'app',
    components: {
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
    }
}
</script>

<style>
    body {
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
</style>
