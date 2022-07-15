<template>
    <draggable
        class="list-group"
        tag="ul"
        v-model="todoList"
        v-bind="dragOptions"
        @start="drag = true"
        @end="drag = false">
        <transition-group type="transition" :name="!drag ? 'flip-list' : null">
            <li
                class="list-group-item"
                v-for="todo in todoList"
                :key="todo.id">
                {{ todo.task }}
            </li>
        </transition-group>
    </draggable>
</template>

<script>
export default {
    name: "todolist"
}
</script>

<style>

</style>