<template>
  <div class="task">
    <h3>{{ task.title }}</h3>
    <p>{{ task.text }}</p>
    <span>#{{ task.id }}</span>
  </div>
</template>

<script setup lang="ts">
interface Task {
  id: number;
  title: string;
  text: string;
}

defineProps<{
  task: Task;
}>();
</script>

<style scoped>
.task {
  border: 1px solid #ccc;
  padding: 15px;
  margin: 10px 0;
  background: white;
}

.task h3 {
  margin: 0 0 8px 0;
  color: #333;
}

.task p {
  margin: 0 0 5px 0;
  color: #666;
}

.task span {
  color: #999;
  font-size: 12px;
}
</style>