<template>
  <div>
    <div class="todos" v-for="todo in props.todos" :key="todo.id">
      <h4>{{ todo.title }}</h4>
      <button v-if="!todo.isComplited" @click="deleteTodo(todo.id)">✖️</button>
      <span v-else>✔️</span>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["todos"]);
const emit = defineEmits();
const deleteTodo = (idx) => {
  emit('deleteTodo', idx)
};
</script>

<style scoped>
.todos {
  padding-top: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 400px;
  border: 1px solid greenyellow;
}
</style>
