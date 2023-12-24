<template>
    <form @submit.prevent="addTask" class="flex space-x-3">
        <input type="text" id="newTask" v-model="newTask" class="border-2 px-3"/>
        <button type="submit" class="bg-blue-500">Button</button>
    </form>
</template>

<script>

export default {
    data() {
        return {
            newTask : '',
        }
    },
    methods: {
        addTask() {
            this.$emit('taskAdded', this.newTask)
            this.newTask = ''
        }
    },
}
</script>