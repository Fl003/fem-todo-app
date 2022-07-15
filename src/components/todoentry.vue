<template>
    <div class="todo-wrapper">
        <customcheckbox
            :checked="done"
            @toggle="toggle"/>
        
        <p id="task">{{todo}}</p>

        <div id="delete-wrapper">
            <img src="../assets/icon-cross.svg" alt="delete">
        </div>
    </div>
</template>

<script>
import customcheckbox from './customcheckbox.vue'

export default {
    name: "todoentry",
    data() {
        return {
            done: this.checked
        }
    },
    props: {
        id: Number,
        checked: Boolean,
        todo: String
    },
    components: {
        customcheckbox
    },
    methods: {
        toggle(value) {
            this.done = value;
        },
        delete() {
            this.$emit('delete', this.id);
        }
    }
}
</script>

<style scoped>
.todo-wrapper {
    width: 100%;
    height: 60px;
    display: flex;
    align-items: center;
    background-color: white;
    border-top: 1px solid var(--l-very-light-grey-blue);
}

#task {
    width: 100%;
}

#delete-wrapper {
    margin-left: 15px;
    margin-right: 20px;
}

#delete-wrapper img {
    width: 15px;
    height: 15px;
    opacity: 0;
    transition: all 0.05s linear;
}

.todo-wrapper:hover #delete-wrapper img {
    opacity: 1;
}
</style>