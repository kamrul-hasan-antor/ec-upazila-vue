<script setup>
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  icon: { type: [Object, Function], default: null },
  color: { type: String, default: "#009951" },
});
</script>

<template>
  <div
    class="bg-white rounded-lg p-5 border-2 border-[#F3F4F6] flex items-start gap-4"
  >
    <div
      class="rounded-lg w-10 h-10 flex items-center justify-center shrink-0"
      :style="{ backgroundColor: color + '18' }"
    >
      <component :is="icon" :style="{ color }" class="w-5 h-5" />
    </div>
    <div>
      <p class="font-semibold mb-1.5" :style="{ color }">
        {{ title }}
      </p>
      <p class="text-[#6B7280] text-sm">{{ description }}</p>
    </div>
  </div>
</template>
