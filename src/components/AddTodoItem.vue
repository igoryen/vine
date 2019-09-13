<template>
    <div>
        <form @submit="aggregateItem">
            <input type="text" v-model="title" name="title" placeholder="Add a Todo item...">
            <input type="submit" value="Hand In" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: "AppendItem",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        aggregateItem( e ) {
            // method defined
            e.preventDefault();
            const brandNewItem = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            // Send it up to parent
            this.$emit('add-item', brandNewItem);
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }
    input[type="text"] {
        flex: 10px;
        padding: 5px;
    }
    input[type="submit"] {
        flex: 2;
    }
</style>