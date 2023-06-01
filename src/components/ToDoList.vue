<template>
  <div>
    <h1>Todo List</h1>
    <input
      v-model="newTodo"
      placeholder="Add a new todo"
      @keyup.enter="addTodo"
    />
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="deleteTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo !== "") {
        this.todos.push(this.newTodo);
        this.newTodo = "";
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
ul {
  padding: 0;
}
li {
  list-style: none;
  margin-bottom: 5px;
  font-size: 30px;
}
button {
  margin-left: 10px;
}
</style>
