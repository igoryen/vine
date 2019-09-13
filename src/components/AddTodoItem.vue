<template>
    <div>
        <form>
            <input type="text" name="title" placeholder="Add a Todo item...">
            <input type="submit" value="Hand In" class="btn">
        </form>
    </div>
</template>

<script>
export default {
    name: "AppendItem"
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