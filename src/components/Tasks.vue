<template>
  <div id="tasks-container">
    <div v-bind:key="task.id" v-for="task in tasks">
      <Task v-bind:task="task" v-on:del-task="$emit('del-task', task.id)"/>
    </div>
  </div>
</template>

<script>
  import Task from './Task.vue';

  export default {
    name: "Tasks",
    components: {
      Task
    },
    props: ["tasks"]
  }

</script>

<style scoped>
  #tasks-container {
    margin-top: 30px;
  }

</style>
