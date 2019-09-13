<template>
    <div class="list-item" v-bind:class="{'is-complete':item.completed}">
        <p>{{item.title}}</p>
    </div>
</template>

<script>
export default {
    name: "IndividualItem",
    props: ["item"]
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