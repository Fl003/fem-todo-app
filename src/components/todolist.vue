<template>
    <div class="todolist-wrapper">
        <draggable
            class="list-group"
            tag="ul"
            v-model="listToShow"
            v-bind="dragOptions"
            @start="drag = true"
            @end="drag = false">
            <transition-group type="transition" :name="!drag ? 'flip-list' : null">
                <todoentry
                    class="list-group-item"
                    v-for="todo in listToShow"
                    :key="todo.id"
                    :id="todo.id"
                    :todo="todo.task"
                    :done="todo.checked"/>
            </transition-group>
        </draggable>
    </div>
</template>

<script>
import draggable from 'vuedraggable';
import todoentry from './todoentry.vue'

export default {
    name: "todolist",
    data() {
        return {
            drag: false
        }
    },
    props: {
        listToShow: Array
    },
    components: {
        draggable,
        todoentry
    },
    computed: {
        dragOptions() {
            return {
                animation: 200,
                group: "description",
                disabled: false,
                ghostClass: "ghost"
            };
        }
    }
}
</script>

<style>
.todolist-wrapper {
    border-radius: 5px;
    width: 100%;
    height: auto;
    overflow: hidden;
    box-shadow: rgba(17, 12, 46, 0.05) 0px 48px 100px 0px;
}
</style>