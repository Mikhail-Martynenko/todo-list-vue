<template>
  <div class="inputCustom">
    <input type="text" placeholder="Add a task" v-model="inputText">
    <button @click="addTask">Add</button>
  </div>
</template>

<script setup>
import {ref} from "vue";

const props = defineProps({
  tasks: {
    type: Array,
  },
});
const inputText = ref('');
const addTask = () => {
  if (inputText.value.trim() === '') return;

  props.tasks.push({
    text: inputText.value,
    completed: false
  });
  inputText.value = '';
}
</script>

<style scoped>
.inputCustom input {
  padding: 10px;
}
</style>