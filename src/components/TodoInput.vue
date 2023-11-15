<template>
  <div>
    <input type="text" v-model="inputTodo" class="input" v-on:keyup.enter="addTodo"/>
    <button @click="addTodo">➕</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const inputTodo = ref("");
const emit = defineEmits();

const addTodo = () => {
  emit('addTodo', inputTodo.value)
  inputTodo.value = '';
};
</script>

<style scoped>

.input {
  min-width: 370px;
}
</style>
