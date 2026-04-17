<script setup>
import { ArrowRight } from "@lucide/vue";

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
  <div class="bg-white py-5 px-5 rounded-lg shadow">
    <component :is="icon" />
    <p :style="{ color }" class="text-lg font-semibold mt-3">
      {{ title }}
    </p>

    <p class="text-sm text-[#6B7280] mt-2">
      {{ description }}
    </p>

    <a
      :href="url"
      :style="{ color }"
      class="mt-4 text-sm flex items-center gap-0.5 font-medium group"
    >
      বিস্তারিত দেখুন
      <arrow-right
        class="size-4 group-hover:ml-1 transition-all duration-200"
      />
    </a>
  </div>
</template>
