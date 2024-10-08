<template>
  <div>
    <input 
      type="text" 
      :value="task.text" 
      @input="$emit('editTask', $event.target.value)"
    />
    <button @click="$emit('deleteTask')">Delete</button>
  </div>
</template>

<script>
export default {
  props: {
    task: Object
  }
}
</script>

<style scoped>
input {
  border: none;
  background-color: #333;
  color: #fff;
  padding: 5px;
  margin-right: 10px;
}

input:focus {
  outline: none;
}

button {
  background-color: #ff5555;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}

button:hover {
  background-color: #cc0000;
}
</style>
