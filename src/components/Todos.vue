<template>
    <div>
        <div v-bind:key="item.id" v-for="item in list">
            <!-- <h3>{{item.title}}</h3> -->
            <ListPoint v-bind:item="item" v-on:del-item="$emit('del-item', item.id)"/>
        </div>
    </div>
</template>

<script>
import ListPoint from "./TodoItem.vue";
export default {
    name: "MyItems",
    components: {
        ListPoint
    },
    props: ["list"]
}
</script>

<style scoped>

</style>