<template>
  <div class="todoBox">
    <h1>Todo List</h1>
    <InputWithAction :tasks="tasks"/>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <input type="checkbox" v-if="!task.completed" @change="completedTask(index)">
        <span :class="{ completed: task.completed }">{{ task.text }}</span>
        <button class="delete-button" @click="deleteTask(index)">❌</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import {ref} from "vue";
import InputWithAction from "@/components/InputWithAction.vue";

const tasks = ref([])

const deleteTask = (index) => tasks.value.splice(index, 1)

const completedTask = (index) => tasks.value[index].completed = true;

</script>

<style scoped>
.todoBox {
  display: flex;
  flex-direction: column;
  border: 1px solid hsla(160, 100%, 37%, 1);
  color: hsla(160, 100%, 37%, 1);
  padding: 25px;
  gap: 20px;
}

h1 {
  text-align: center;
}

ul {
  padding: 0;
}

button {
  padding: 10px;
  background-color: hsla(160, 100%, 37%, 1)
}

li {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.completed {
  text-decoration: line-through;
  color: gray;
}

.delete-button {
  border: none;
  background: transparent;
  cursor: pointer;
}
</style>
