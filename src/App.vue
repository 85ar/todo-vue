<template>
  <main>
    <TodoInput @addTodo="addTodo" />
    <TodoList :todos="todos" @deleteTodo="deleteTodo" />
  </main>
</template>

<script setup>
import { reactive } from "vue";
import TodoList from "./components/TodoList.vue";
import TodoInput from "./components/TodoInput.vue";

const todos = reactive([
  {
    id: 0,
    title: "todo1",
    isComplited: false,
  },
  {
    id: 1,
    title: "todo2",
    isComplited: false,
  },
  {
    id: 2,
    title: "todo3",
    isComplited: true,
  },
]);

const addTodo = (todoInput) => {
  todos.push({ id: todos.length + 1, title: todoInput, isComplited: false });
};

const deleteTodo = (id) => {
console.log('id', id);
const i = todos.indexOf((todo => todo.id === id))
todos.splice(i, 1)
}
</script>

<style lang="scss" scoped></style>
