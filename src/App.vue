<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <TodoList v-bind:todo_list="todo_list" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoList,
  },
  methods: {
    deleteTodo(todo_id) {
      this.todo_list = this.todo_list.filter(t => t.id != todo_id)
    },
    addTodo(todo_id) {
      this.todo_list = this.todo_list.filter(t => t.id != todo_id)
    },
  },
  data() {
    return {
      todo_list: [
        {
          id: 0,
          title: "Kiss girlfriend",
          completed: true,
        },
        {
          id: 1,
          title: "Kiss girlfriend again",
          completed: false,
        },
        {
          id: 2,
          title: "Todo number three",
          completed: false,
        },
      ],
    };
  },
};
</script>
