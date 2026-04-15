<!-- Options API -->
<script>
export default {
  data() {
    return {
      message: "Hello John Doe",
      status: "active",
      tasks: [
        { id: 1, text: "Task 1" },
        { id: 2, text: "Task 2" },
        { id: 3, text: "Task 3" },
      ],

      link: "https://www.google.com",
    };
  },

  methods: {
    toggleStatus() {
      if (this.status === "active") {
        this.status = "pending";
      } else if (this.status === "pending") {
        this.status = "inactive";
      } else {
        this.status = "active";
      }
    },
  },
};
</script>

<template>
  <!-- show a value -->
  <h1 class="text-red-500 font-bold text-9xl">{{ message }}</h1>

  <!-- show conditional rendering -->
  <p v-if="status === 'active'">user is active</p>
  <p v-else-if="status === 'pending'">user is pending</p>
  <p v-else>user is inactive</p>

  <!-- array loop -->
  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task.id">{{ task?.text }}</li>
  </ul>

  <!-- link -->
  <!-- <a v-bind:href="link" target="_blank">Link</a> -->
  <a :href="link" target="_blank">Link</a>

  <br />

  <!-- events -->
  <!-- <button v-on:click="toggleStatus" class="cursor-pointer">
    Change Status
  </button> -->
  <button @click="toggleStatus" class="cursor-pointer">Change Status</button>
</template>
