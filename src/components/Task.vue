<template>
  <div class="task" v-bind:class="{'completed':task.completed}">
    <p>
      <input type="checkbox" v-on:change="showAsComplete">
      {{task.description}}
      <button @click="$emit('del-task', task.id)"
      class="delete">X</button>
    </p>
  </div>
</template>

<script>

  export default {
   name: 'Task',
   props: ['task'],
   methods: {
     showAsComplete() {
      this.task.completed = !this.task.completed;
     }
   }
 }


</script>

<style>
  .task {
  background: crimson;
  padding: 20px;
  width: 300px;
  margin: 0 auto;
  color: white;
  text-align: center;
  font-size: 20px;
  }

  .completed {
   background: green;
  }

  .delete {
   background: white;
   color: black;
   font-weight: bold;
   border: none;
   padding: 5px 9px;
   border-radius: 3px;
   cursor: pointer;
   float: right;
   font-size: 12px;
  }

</style>
