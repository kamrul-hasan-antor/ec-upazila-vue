<script setup>
import { defineProps } from "vue";

defineProps({
  title: {
    type: String,
    default: "Become a Vue Dev",
  },
  subtitle: {
    type: String,
    default: "Find the Vue job that fits your skills and needs",
  },
  // title: String, if dont want defalut props, we can set it like this
  // subtitle: String
});
</script>

<template>
  <div class="bg-green-700 py-20 mb-4">
    <div
      class="max-w-7xl mx-auto flex flex-col items-center px-4 sm:px-6 lg:px-8"
    >
      <div class="text-center">
        <h1 class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl">
          {{ title }}
        </h1>
        <p class="my-4 text-xl text-white">
          {{ subtitle }}
        </p>
      </div>
    </div>
  </div>
</template>
