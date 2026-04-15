<!-- Composition API -->

<!-- in composition API, we use setup function to define our component's logic and return what we want to expose to the template, or write setup attribute to do the same. no need to return  -->

<script setup>
import { onMounted, ref } from "vue";

const name = "John Doe";
const status = ref("active");
const tasks = ref([
  { id: 1, text: "Task 1" },
  { id: 2, text: "Task 2" },
  { id: 3, text: "Task 3" },
  { id: 4, text: "Task 4" },
]);
const newTask = ref("");

const toggleStatus = () => {
  if (status.value === "active") {
    status.value = "inactive";
  } else if (status.value === "inactive") {
    status.value = "pending";
  } else {
    status.value = "active";
  }
};

const addTask = () => {
  if (newTask.value.trim() === "") return;

  const newTaskObj = {
    id: tasks.value.length + 1,
    text: newTask.value,
  };

  tasks.value.push(newTaskObj);
  newTask.value = "";
};

const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};

onMounted(async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await response.json();
    console.log(data)
    tasks.value = data;
  } catch (error) {
    console.error("Error fetching data:", error);
  }
});
</script>

<template>
  <!-- show a value -->
  <h1 class="text-red-500 font-bold text-9xl">{{ name }}</h1>

  <!-- show conditional rendering -->
  <p v-if="status === 'active'">user is active</p>
  <p v-else-if="status === 'pending'">user is pending</p>
  <p v-else>user is inactive</p>

  <form @submit.prevent="addTask">
    <label for="newTask">New Task</label>
    <input type="text" name="newTask" v-model="newTask" class="border" />
    <button
      type="submit"
      class="cursor-pointer bg-blue-500 text-white px-4 py-px rounded"
    >
      Submit
    </button>
  </form>

  <!-- array loop -->
  <h3>Tasks</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task.id" class="mt-2">
      <span>{{ task?.title }}</span>
      <button
        @click="deleteTask(index)"
        class="cursor-pointer bg-red-500 text-white px-2 py-px rounded ml-1"
      >
        X
      </button>
    </li>
  </ul>

  <!-- link -->
  <!-- <a v-bind:href="link" target="_blank">Link</a> -->
  <a :href="link" target="_blank">Link</a>

  <br />

  <!-- events -->
  <!-- <button v-on:click="toggleStatus" class="cursor-pointer">
    Change Status
  </button> -->
  <button
    @click="toggleStatus"
    class="cursor-pointer bg-blue-500 text-white px-4 py-px rounded"
  >
    Change Status
  </button>
</template>
