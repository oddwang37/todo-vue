<template>
  <div id="app">
    <h1>Todo application</h1>
    <hr />
    <TodoList @remove-todo="removeTodo" :todos="todos" />
    <AddTodo @add-todo="addTodo"></AddTodo>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
import AddTodo from '@/components/AddTodo';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        { id: 1, title: 'Купить хлеб', completed: true },
        { id: 2, title: 'Забрать сына с садика', completed: false },
        { id: 3, title: 'Отправить отчёт', completed: false },
      ],
      setCompleted(id) {
        this.todos[id].completed = !this.todos[id].completed;
      },
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(task) {
      this.todos.push(task);
    },
  },
  components: {
    TodoList,
    AddTodo,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
