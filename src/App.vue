<template>
<div class="container">
  <Header title="Task List" />
  <Tasks 
    @delete-task="deleteTask" 
    @toggle-reminder="toggleReminder" 
    :tasks="tasks"
   />
</div>
</template>

<script>
import Header from './components/layouts/Header'
import Tasks from './components/Tasks'

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data(){
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(taskId){
      this.tasks = this.tasks.filter((task) => task.id !== taskId);
    },
    toggleReminder(taskId){
      this.tasks = this.tasks.map((task) => 
      task.id === taskId ? { ...task, reminder: !task.reminder} : task
    )}
  },
  created(){
    this.tasks= [
      {
        id: 1,
        text: "test text",
        day: "1st test day", 
        reminder: false
      },
      {
        id: 2,
        text: "test 2 text",
        day: "1st 2 test day",
        reminder: true
      },
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
