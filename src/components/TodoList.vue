<template>
  <div>
    <div v-bind:key="t.id" v-for="t in todo_list">
      <TodoItem v-bind:todo="t" v-on:del-todo="$emit('del-todo', t.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "TodoList",
  components: {
    TodoItem,
  },
  props: ["todo_list"],
};
</script>

<style></style>
