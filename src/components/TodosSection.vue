<template>
  <div id="todos-section-wrapper">
    <div>Todos</div>
    <Todo
      v-for="todo in todos"
      :key="todo.id"
      :id="todo.id"
      :title="todo.title"
      :time="todo.time"
      @delete-todo="(id) => this.$emit('delete-todo', id)"
    />
  </div>
</template>

<script>
import Todo from "./Todo.vue";
export default {
  name: "TodosSection",
  props: {
    todos: Array,
  },
  components: {
    Todo,
  },
};
</script>

<style>
#todos-section-wrapper {
  background-color: rgb(230, 230, 230);
  width: 100%;
  min-height: 30px;
  /* margin-top: 15px; */
}
</style>
