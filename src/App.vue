<template>
  <div class="app">
    <input v-model="search" placeholder="Поиск" />
    <input v-model="newTaskName" placeholder="Введите название таски" />
    <button @click="createNewTask">Сохранить</button>
    <ul>
      <li :key="item.id" v-for="item in filteredTasks">
        <TaskCard :name="item.name" @save="changeTask(item.id, $event)"></TaskCard>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';
import TaskCard from './components/Hometask/TaskCard.vue';

const search = ref(null)
const tasks = ref([])

const newTaskName = ref(null)

function createNewTask() {
  const newTask = { id: Date.now(), name: newTaskName.value }
  tasks.value.push(newTask)
}

function changeTask(taskId, newTaskName) {
  const task = tasks.value.find(task => task.id === taskId)
  if (task) {
    task.name = newTaskName
  }
}

const filteredTasks = computed(() => {
  if (search.value === null) {
    return tasks.value
  }
  return tasks.value.filter((task) => task.name.includes(search.value))
})

// const filterTask = computed(() => {
//   if (search.value === null) {
//     return tasks.value
//   }
//   else {
//     return tasks.value.map(function (task) {
//       const taskName = task.name
//       const isNeedPush = taskName.startsWith(search.value)
//       if (isNeedPush) {
//         return taskName
//       }
//       else {
//         return console.log("НЕТУ")
//       }
//     }
//     )
//   }
// })

</script >

<style >
.app {
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style >





