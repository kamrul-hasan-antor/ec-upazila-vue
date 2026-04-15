<script setup>
import { defineProps } from "vue";

defineProps({
  title: {
    type: String,
    default: "",
  },
  description: {
    type: String,
    default: "",
  },
  color: {
    type: String,
    default: "#009951",
  },
  url: {
    type: String,
    default: "/",
  },
  icon: {
    type: Object,
    default: null,
  },
});
</script>

<!-- border border-[rgba(145,158,171,0.3)] shadow-[0px_0px_15px_0px_#00000010] -->
<template>
  <div class="bg-white p-3 rounded-lg shadow">
    <component
      :is="icon"
      :style="{ color: color, width: '30px', height: '30px' }"
    />
    <p>{{ title }}</p>
  </div>
</template>
