<template>
  <div class="container">
    <h2 class="todo-list-title">My Tasks</h2>
    <div class="in-liner">
      <h4>Enter a new task:</h4>
      <div>
        <input type="text" v-model="task" @keyup.enter="addTask">
        <button @click="addTask">Add Task</button>
      </div>
    </div>
  </div>

  <table class="task-table">
    <thead>
      <tr>
        <th class="task-header">Task</th>
        <th>Pending</th>
        <th>In Progress</th>
        <th>Done</th>
        <th>Remove</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(task, index) in tasks" :key="index">
        <td>{{ task.name }}</td>
        <td><input type="radio" :name="'status' + index" value="pending" v-model="task.status"></td>
        <td><input type="radio" :name="'status' + index" value="inProgress" v-model="task.status"></td>
        <td><input type="radio" :name="'status' + index" value="done" v-model="task.status"></td>
        <td><button @click="removeTask(index)">Remove</button></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
name: 'HelloWorld',
data() {
  return {
    tasks: [
      { name: 'Finish To-Do List project', status: 'pending' },
      { name: 'Sleep', status: 'pending' },
      { name: 'Become a Fisherman', status: 'pending' }
    ],
    task: ''
  }
},
methods: {
  addTask() {
    if (this.task) {
      this.tasks.push({ name: this.task, status: 'pending' });
      this.task = '';
    }
  },
  removeTask(index) {
    this.tasks.splice(index, 1);
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
margin: 0 25%;
background-color: #f2f2f2;
}

.task-table {
margin: 0 25%;
width: 50%;
border-collapse: collapse;
background-color: #f2f2f2;
}

.task-table th,
.task-table td {
padding: 8px;
border-bottom: 1px solid #ddd;
}

.task-table th {
background-color: #f2f2f2;
font-weight: bold;
border: 1px solid #000000;
}

.task-table td {
text-align: left;
border: 1px solid #000000;
}

.task-table th.task-header {
width: 100%;
}

.task-table th:not(.task-header) {
width: 15%;
}

.in-liner {
display: flex;
justify-content: space-between;
align-items: center;
padding: 10px;
margin: 0 10%;
}

.todo-list-title {
padding-top: 10px;
margin: 0;
border-top: 2px solid #000000;
}
</style>
