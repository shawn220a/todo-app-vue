<script>
let count = 0;
export default {
  data() {
    return {
      todoList: [],
    };
  },
  methods: {
    addTodo(t) {
      this.todoList.push({ id: count, message: t });
      count++;
    },
    removeTodo(item) {
      let array = this.todoList.filter((x) => x.id !== item.id);
      this.todoList = array;
    },
  },
};
</script>

<template>
  <!-- Todo List -->
  <input v-model="text" />
  <button @click="addTodo(text)">Add Todo</button>
  <li v-for="todo in todoList">
    {{ todo.message }}
    <button @click="removeTodo(todo)">Delete</button>
  </li>
</template>

<style scoped></style>
