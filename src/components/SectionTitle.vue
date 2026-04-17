<script setup>
import { cn } from "@/utils/cn";
defineProps({
  title: { type: String },
  description: { type: String, default: "" },
  extendedClass: { type: String, default: "" },
});
</script>

<template>
  <div class="flex flex-col gap-2">
    <div class="flex items-center gap-3">
      <div class="h-5.5 w-1 bg-[#009951] rounded"></div>
      <h2
        :class="
          cn('text-base md:text-lg font-semibold text-[#009951]', extendedClass)
        "
      >
        {{ title }}
      </h2>
    </div>

    <p v-show="description.length" class="text-sm text-[#6B7280]">
      {{ description }}
    </p>
  </div>
</template>
