<template>
  <div id="app">
    <h1 id="heading">My Tasks</h1>
    <Tasks v-bind:tasks="tasks" v-on:del-task="deleteTask"/>
  </div>
</template>

<script>
import Tasks from './components/Tasks'

export default {
  name: 'app',
  components: {
    Tasks
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          description: 'Laundry',
          completed: true
        },
        {
          id: 2,
          description: 'Ironing',
          completed: false
        },
        {
          id: 3,
          description: 'Food shop',
          completed: true
        },
        {
          id: 4,
          description: 'Clothes shop',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    }
  }
}
</script>

<style>
  #heading {
    text-align: center;
    margin-top: 20px;
    color: orange;
  }
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
      background: black;
    font-family: Arial, Helvetica, sans-serif;
  }
</style>
