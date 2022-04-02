<template>
  <div :class="{ done: todo.completed }">
    <li>{{ todo.title }}</li>
    <input
      v-on:change="todo.completed = !todo.completed"
      type="checkbox"
      :checked="todo.completed"
    />
    <button v-on:click="$emit('remove-todo', todo.id)">удалить</button>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  methods: {},
};
</script>
