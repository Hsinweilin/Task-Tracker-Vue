<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @btn-click="$emit('toggle-add-task')"  :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'"/><!--Not just a button tage, it's a actual object from export default-->
        <Button text="Update Task" color="blue"/>
        <Button text="Delete Task" color="red"/>
    </header>
</template>

<script>
import Button from './Button'

    export default{
        name: 'Header',
        props: {
            title: String,
            showAddTask: Boolean
        },
        components: {
            Button
        },
        emits: ['toggle-add-task']
    }
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>