<template>
  <h1>To-do list on Vue</h1>
  <TodoList
    :todos="todos"
    :handleAddNewTodo="handleAddNewTodo"
    :handleIsCompletedTodo="handleIsCompletedTodo"
    :handleRemoveTodo="handleRemoveTodo"
  />
</template>

<script>
import TodoList from '@/components/TodoList';
const todos = [];
export default {
  name: 'App',
  components: {
    TodoList,
  },
  data() {
    return {
      todos,
    };
  },
  methods: {
    handleAddNewTodo(newTodo) {
      this.todos.push(newTodo);
    },
    handleRemoveTodo(id) {
      this.todos = [...this.todos.filter((item) => item.id !== id)];
    },
    handleIsCompletedTodo(id) {
      this.todos.forEach((todo) => {
        if (todo.id === id) {
          todo.comleted = !todo.comleted;
        }
      });
    },
  },
};
</script>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css');
@import url('@/fonts/fonts.css');
#app {
  /* Avenir, Helvetica, Arial, sans-serif */
  --dark-bg: #1c1b1f;
  --prim-90: #eaddff;
  --prim-80: #d0bcff;
  --prim-c-30: #4f378b;
  --prim-c-90: #eaddff;
  font-family: 'Manrope-Regular';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  grid-template-rows: 100px 1fr 40px;
  min-height: 100vh;
  background-color: var(--dark-bg);

  ::-webkit-scrollbar {
    display: none;
  }
}
h1 {
  margin: 0;
  font-size: 3.2rem;
  font-weight: 700;
  padding-top: 25px;
  color: var(--prim-90);
}
</style>
