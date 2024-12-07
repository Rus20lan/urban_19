<template>
  <div class="container">
    <AddForm @send-add-todo="handleAddNewTodo" />
    <ul>
      <TodoItem
        v-for="todo in todos"
        v-bind:todo="todo"
        :key="todo.id"
        @send-completed="handleIsCompletedTodo"
        @send-remove-todo="handleRemoveTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';
import AddForm from './AddForm.vue';
export default {
  name: 'TodoList',
  props: [
    'todos',
    'handleAddNewTodo',
    'handleIsCompletedTodo',
    'handleRemoveTodo',
  ],
  components: {
    TodoItem,
    AddForm,
  },
};
</script>

<style scoped>
.container {
  margin: 0 auto;
  width: 70%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  gap: 40px;
}
ul {
  width: 100%;
  margin: 0px auto;
  list-style: none;
  margin: 0 auto;
  padding: 2rem;
}
</style>
