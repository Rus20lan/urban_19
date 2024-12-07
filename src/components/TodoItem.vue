<template>
  <li class="todo">
    <span v-if="isCompleted" class="textTodo markDone"
      ><del>{{ todo.text }}</del></span
    >
    <span v-else class="textTodo">{{ todo.text }}</span>
    <div class="controlWrapper">
      <label class="control_label" for="checkbox">
        <input
          v-model="isCompleted"
          type="checkbox"
          :checked="isCompleted"
          @change="sendIsCompletedTodo"
        />
      </label>
      <button @click="sendRemoveTodo" class="btn">
        <img src="@/images/delete.svg" alt="del" />
      </button>
    </div>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  data() {
    return {
      isCompleted: this.todo.comleted,
      id: this.todo.id,
    };
  },
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  methods: {
    sendIsCompletedTodo() {
      this.$emit('send-completed', this.id);
    },
    sendRemoveTodo() {
      this.$emit('send-remove-todo', this.id);
    },
  },
};
</script>

<style scoped>
del {
  text-decoration: line-through;
  text-decoration-color: red;
  vertical-align: middle;
}
.todo {
  margin: 10px;
  width: 100%;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex: 0 0 auto;
  border-bottom: 1px solid var(--prim-c-90);
}
.markDone::before {
  content: url('@/images/shape.svg');
  display: inline-block;
  width: 20px;
  height: 20px;
  margin-right: 10px;
}
.textTodo {
  font-size: 2.1rem;
  color: var(--prim-80);
  overflow-x: scroll;
}
.controlWrapper {
  align-self: center;
  display: flex;
  width: auto;
  justify-content: space-between;
  align-items: center;
  width: auto;
}
.controlLabel {
  padding: 10px;
}
input[type='checkbox'] {
  width: 24px;
  height: 24px;
}
input[type='checkbox']:checked {
  accent-color: var(--prim-80);
}
.btn {
  margin: 5px;
  padding: 2px;
  width: 32px;
  height: 32px;
  background: var(--prim-80);
  background-repeat: no-repeat;
  border: none;
  border-radius: 100%;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  box-sizing: border-box;
  display: flex;
  align-items: center;
}
.btn img {
  width: 100%;
  height: 100%;

  object-fit: contain;
}
.btn:hover {
  background: var(--prim-80);
}
.btn:active {
  -webkit-transform: scale(0.9);
  -ms-transform: scale(0.9);
  transform: scale(0.9);
  background: var(--prim-c-30);
}
</style>
