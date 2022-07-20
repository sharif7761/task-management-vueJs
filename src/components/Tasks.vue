<template>
  <div :key="task.id" v-for="task in tasks"> 
    <SingleTask
     @delete-task="$emit('delete-task', task.id)"
     @toggle-reminder="$emit('toggle-reminder', task.id)"
     :task="task" />
  </div>
</template>

<script>
import SingleTask from './SingleTask.vue';
export default {
    name: "TaskList",
    props: {
        tasks: Array,
    },
    components: { SingleTask },
    emits: ['toggle-reminder', 'delete-task']
}
</script>