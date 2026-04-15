<script setup>
import logo from "@/assets/logo.svg";
</script>

<template>
  <div class="w-full py-4 bg-green-800">
    <div class="container mx-auto flex items-center justify-between">
      <img :src="logo" alt="logo" class="h-8 w-auto" />

      <div class="flex gap-x-1">
        <a href="/" class="p-2 text-white bg-green-900 rounded">Home</a>
        <a href="/" class="p-2 text-white">Jobs</a>
        <a href="/" class="p-2 text-white">Add Job</a>
      </div>
    </div>
  </div>
</template>
