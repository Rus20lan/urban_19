<template>
  <div class="container">
    <form @submit.prevent ref="addForm">
      <input v-model="text" class="formInput" type="text" />
      <button type="submit" class="formBtn" @click="sendAddNewTodo">
        <img src="@/images/pen.svg" />
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: '',
    };
  },
  methods: {
    sendAddNewTodo() {
      if (this.text) {
        this.$emit('send-add-todo', {
          id: Date.now(),
          text: this.text,
          comleted: false,
        });
        this.text = '';
        this.$refs.addForm.reset();
      }
    },
  },
};
</script>

<style scoped>
.container {
  padding: 2rem;
}
form {
  display: flex;
  justify-content: flex-start;
  gap: 50px;
}
.formInput {
  border-radius: 4px 4px 0 0;
  border: none;
  width: 90%;
  height: 56px;
  background: inherit;
  font-size: 2.1rem;
  border-bottom: 1px solid var(--prim-90);
  color: var(--prim-80);
}
.formInput:focus {
  outline: none;
}
.formBtn {
  border: none;
  border-radius: 8px;
  background: var(--prim-80);
  font-size: 1.5rem;
  text-transform: uppercase;
  color: var(--dark-bg);
  height: 40px;
  align-self: center;
}
.formBtn:hover {
  background: var(--prim-90);
}
.formBtn:active {
  transform: scale(0.9);
  background: var(--prim-c-30);
}
</style>
