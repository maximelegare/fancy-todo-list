<template>
  <div id="layout">
    <div class="layout-margin">
      <Header title="To do list" @toggle-add-task="toggleAddTask"/>
      <InputSection @add-todo="addTodo" v-if="showAddTask"/>
      <TodosSection :todos="todos" @delete-todo="deleteTodo" />
    </div>
  </div>
</template>

<script>
import Header from "./Header.vue";
import InputSection from "./InputSection.vue";
import TodosSection from "./TodosSection.vue";
export default {
  name: "Layout",
  components: {
    Header,
    InputSection,
    TodosSection,
  },
  created(){
      console.log(this.todos)
  },
  data() {
    return {
      todos: [
        {
          id: "1",
          title: "manger",
          time: "10pm",
        },
        {
          id: "2",
          title: "boire",
          time: "1pm",
        },
      ],
      showAddTask:false
    };
  },
  methods: {
    toggleAddTask(){
        this.showAddTask = !this.showAddTask
    },  
    addTodo(todo) {
      const newTodo = {
        ...todo,
        id: Math.floor(Math.random() * 1000000),
      };
      this.todos.push(newTodo)
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => {
        console.log(todo.id);
        return todo.id !== id;
      });
    },
  },
};
</script>

<style scoped>
#layout {
  width: 35%;
  margin: 0 auto;
}
</style>
