<template>
    <div class="list-item" v-bind:class="{'is-complete':item.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{item.title}}
            <button @click="$emit('del-item', item.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "IndividualItem",
    props: ["item"],
    methods: {
        markComplete() {
            this.item.completed = !this.item.completed;
        }
    }
}
</script>

<style scoped>
    .list-item {
        background-color: #f4f4f4;
        padding: 5px;
        margin: 3px;
        border-bottom: 1px dotted #ccc;
    }
    .is-complete {
        text-decoration: line-through;
    }
    .del {
        background-color: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>