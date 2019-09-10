<template>
    <div>
        <h1>My things to do</h1>
        <div v-bind:key="item.id" v-for="item in list">
            <!-- <h3>{{item.title}}</h3> -->
            <ListPoint v-bind:item="item" />
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