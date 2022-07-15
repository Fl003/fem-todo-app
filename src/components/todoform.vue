<template>
    <div class="input-wrapper">
        <customcheckbox
            @toggle="toggle"/>
        <input type="text" placeholder="Create a new todo..." v-model="todo">
    </div>
</template>

<script>
import customcheckbox from './customcheckbox.vue'

export default {
    name: "todoform",
    data() {
        return {
            done: false,
            todo: ""
        }
    },
    components: {
        customcheckbox
    },
    methods: {
        toggle(value) {
            this.done = value;
        }
    }
}
</script>

<style>
.input-wrapper {
    width: 100%;
    height: 60px;
    display: flex;
    align-items: center;
    border-radius: 5px;
    background-color: white;
    margin: 30px 0px;
    margin-top: 40px;
}

input[type="text"] {
    width: 100%;
    border: none;
    outline: none;
    padding: 10px;
    color: var(--l-dark-grey-blue);
    caret-color: var(--primary-blue);
}
</style>