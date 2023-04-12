<template>
    <div v-for="task in tasks" v-bind:key="task.id"><!--the first task just one element in a iteration, can be changed to any value like abc, v-bind:key give each iteration a specific key from it's given id, can be used later-->
        <!--<h3>{{ task.text }}</h3>, access that specific iteration and access the variable text-->
        <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"/><!--first task, task object of Task component, second task, each task that iterate above-->
    </div><!--emit can go level by level-->
</template>

<script>
import Task from './Task'

export default{
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        Task,
    },
    emits: ['delete-task', 'toggle-reminder'],
}
</script>
<!--Actively define emits and the emitted event!-->