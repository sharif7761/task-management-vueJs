<template>
  <div :key="task.id" v-for="task in tasks"> 
    <SingleTask :task="task" />
  </div>
</template>

<script>
import SingleTask from './SingleTask.vue';
export default {
    name: "TaskList",
    props: {
        tasks: Array,
    },
    components: { SingleTask }
}
</script>