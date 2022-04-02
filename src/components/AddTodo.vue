<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="inputValue" />
    <button>Добавить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      inputValue: '',
    };
  },
  methods: {
    onSubmit() {
      if (this.inputValue.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.inputValue,
          completed: false,
        };
        this.$emit('add-todo', newTodo);
      }
    },
  },
};
</script>
