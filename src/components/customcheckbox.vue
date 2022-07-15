<template>
    <div class="checkbox-wrapper">
        <div id="checkbox" @click="toggle" :class="{ checked: done }">
            <img src="../assets/icon-check.svg" alt="check" v-if="done">
        </div>
    </div>
</template>

<script>
export default {
    name: "customcheckbox",
    data() {
        return {
            done: this.checked,
        }
    },
    props: {
        checked: Boolean
    },
    methods: {
        toggle() {
            this.done = !this.done;
            this.$emit('toggle', this.done);
        }
    }
}
</script>

<style>
#checkbox {
    position: relative;
    margin-left: 20px;
    margin-right: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 25px;
    height: 25px;
    border-radius: 50%;
    border: solid 1px var(--l-light-grey-blue);
}

#checkbox.checked {
    background: var(--background-gradient);
    border: none;
}

#checkbox:hover::before,
#checkbox:hover::after {
    opacity: 1;
}

#checkbox.checked:hover::before,
#checkbox.checked:hover::after {
    opacity: 0;
}

#checkbox::before {
    position: absolute;
    top: -1px;
    left: -1px;
    content: '';
    width: 25px;
    height: 25px;
    border-radius: 15px;
    background: var(--background-gradient);
    opacity: 0;
}

#checkbox::after {
    position: absolute;
    content: '';
    background-color: white;
    border-radius: 15px;
    top: 0;
    left: 0;
    width: 23px;
    height: 23px;
    opacity: 0;
}
</style>