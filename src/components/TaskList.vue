<template>
    <div :key= "task.id" v-for= "task in tasks">
        <TaskListItem 
        :task= "task" 
        @delete-task= "$emit('delete-task', task.id)"
        @toggle-reminder= "$emit('toggle-reminder', task.id)"
        />
    </div>
</template>

<script>
import TaskListItem from './TaskListItem'

export default {
    name: 'TaskList',
    props: {
        tasks: Array
    },
    components: {
        TaskListItem 
    }, 
    emits: ['delete-task', 'toggle-reminder']
}
</script>