<template>
  <div>
    <h3>My Todo</h3>
    <input v-model="newTodo" type="text" placeholder="Input here..." />
    <button @click="addTodo">ADO</button>
    <h5>ToDo List</h5>

    <ul>
      <li v-for="(todo, i) in todos" v-bind:key="i">
        {{ todo }}
        <button @click="deleteToDo(i)">DELETE</button>
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
      if (this.newTodo === "") return;
      this.todos.push(this.newTodo);
      this.newTodo = "";
    },
    deleteToDo(i) {
      this.todos.splice(i, 1);
    },
  },
};
</script>
