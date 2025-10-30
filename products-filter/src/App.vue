<template>
  <div class="app">
    <h1>Список дел</h1>
    <p class="all_task">Всего задач: {{ tasks.length }}</p>
    
    <div class="tasks">
      <TaskItem 
        v-for="task in tasks" 
        :key="task.id" 
        :task="task" 
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import TaskItem from './components/TaskItem.vue';

interface Task {
  id: number;
  title: string;
  text: string;
}

const tasks = ref<Task[]>([
  {
    id: 1,
    title: 'Изучить Vue 3',
    text: 'Освоить основы Vue 3'
  },
  {
    id: 2,
    title: 'Создать компоненты',
    text: 'Практиковаться в создании компонентов'
  },
  {
    id: 3,
    title: 'Изучить Vite',
    text: 'Разобраться с работой Vite'
  },
  {
    id: 4,
    title: 'Добавить стили',
    text: 'Стилизовать компоненты'
  }
]);
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 20px;
  background: #f0f0f0;
}

.all_task{
  color: black;
}

.app {
  max-width: 600px;
  margin: 0 auto;
}

.app h1 {
  color: #333;
  margin-bottom: 10px;
}

.tasks {
  margin-top: 20px;
}
</style>