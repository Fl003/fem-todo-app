<template>
    <div class="input-wrapper">
        <input type="checkbox" v-model="done">
        <input type="text" placeholder="Create a new todo..." v-model="todo">
    </div>
</template>

<script>
export default {
    name: "todoform",
    data() {
        return {
            done: false,
            todo: ""
        }
    }
}
</script>

<style>

</style>