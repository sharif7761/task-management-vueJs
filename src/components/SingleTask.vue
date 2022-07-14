<template>
  <h3>{{task.text}}</h3>
  <h3>{{task.day}}</h3>
  <hr/>
</template>

<script>
export default {
  name: 'SingleTask',
  props: {
    task: Object,
  }
}
</script>