 <!--eslint-disable -->
<template>
<div class="container">
  <HeaderApp @toggle-add-task="ToggleAddTask" title="Task tracker" :showAddTask= 'showAddTask'/>
  <div  v-if="showAddTask">
    <AddTask @add-task="addTask" />
  </div>
 <TaskApp @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
 <FooterApp />
</div>

</template>
<!--eslint-disable -->
<script>
import AddTask from './components/AddTask'
import HeaderApp from './components/HeaderApp'
import TaskApp from  './components/TaskApp'
import FooterApp from  './components/FooterApp'
export default {
  name: 'App',
  components: {
    HeaderApp,
    TaskApp,
    AddTask,
    FooterApp
  },
  data() {
    return {
      tasks: [],
      showAddTask: false
    }
  },
  methods: {
    ToggleAddTask(){
      this.showAddTask = !this.showAddTask
    },
      addTask(task) {
      this.tasks = [...this.tasks, task]

      },
   deleteTask(id) {
    if(confirm("Are you sure")) {
     this.tasks = this.tasks.filter((task) => task.id !== id)
    }
   },
   
   toggleReminder(id) {
    this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task )
   },

   
   
   },
   mounted() {
    this.tasks =  [
      {
      "id": "1",
      "text": "Doctor Appointment",
      "day": "march 1st 2:30pm",
      "reminder": true
    },
     {
      "id": "2",
      "text": "Food shopping", 
      "day": "may 1st 2:30pm",
      "reminder": true
    },
      {
      "id": "3",
      "text": "swimming pool",
      "day": "feb 1st 2:30pm",
      "reminder": false
    }
]

     }
}

</script>
<!--eslint-disable -->
<style>
.container {
  color: black;
  width:400px;
  border: 1px solid grey;
  padding: 20px;
  border-radius: 10px;
  margin: auto;
}
h1{
  text-transform: capitalize;
}
.btn-block {
 display: block;
 width: 100%;
}
.btn{
  border: none;
  padding: 8px 10px;
  cursor: pointer;
  display: inline-block;
  font-size: 15px;
  border-radius: 10px;
  background: black;
  color: white;
  text-transform: capitalize;
}
</style>
