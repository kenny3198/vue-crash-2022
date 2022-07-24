 <!--eslint-disable -->
<template>
<div :key="task.id" v-for="task in tasks">
   <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task= "$emit('delete-task', task.id)" :task="task" />
</div>
</template>
 <!--eslint-disable -->
<script>
import Task from './Task'
export default {
    name: 'TaskApp',
    props: {
        tasks: Array,
    },
    components: {
        Task,
    },
    emits: ["delete-task","toggle-reminder"],
}
</script>
 <!--eslint-disable -->
<style>

</style>
