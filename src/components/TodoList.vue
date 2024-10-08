<template>
  <div>
    <h2>Your Tasks</h2>
    <form @submit.prevent="addTask">
      <input v-model="newTask" placeholder="Add a task" />
      <button type="submit">Add</button>
    </form>
    
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <TodoItem 
          :task="task" 
          @deleteTask="deleteTask(index)" 
          @editTask="editTask(index, $event)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  data() {
    return {
      newTask: '',
      tasks: []
    }
  },
  methods: {
    addTask() {
      if (this.newTask !== '') {
        this.tasks.push({ text: this.newTask });
        this.newTask = ''; // Clear input after adding task
      }
    },
    deleteTask(index) {
      this.tasks.splice(index, 1); // Remove task at index
    },
    editTask(index, newText) {
      this.tasks[index].text = newText; // Edit task text
    }
  },
  components: {
    TodoItem
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}

button {
  background-color: #00ff00;
  color: #000;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}

button:hover {
  background-color: #007700;
}
</style>
