<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <p>
      <input
        type="checkbox"
        v-on:change="toggleComplete"
        :checked="todo.completed"
      />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)">(X)</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    toggleComplete() {
      this.todo.completed = !this.todo.completed;
      //   console.log(this.todo);
    },
  },
};
</script>

<style scoped>
.todo-item {
}

.is-complete {
  text-decoration: line-through;
}
</style>
