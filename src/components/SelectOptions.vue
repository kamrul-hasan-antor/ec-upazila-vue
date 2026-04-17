<script setup>
import { ref } from "vue";
import { ChevronDown } from "@lucide/vue";
import Multiselect from "vue-multiselect";

defineProps({
  options: { type: Array, required: true },
  placeholder: { type: String, default: "Select an option" },
  label: { type: String, default: "name" },
});

const model = defineModel();
const isOpen = ref(false);
</script>

<template>
  <Multiselect
    v-model="model"
    :options="options"
    :placeholder="placeholder"
    :track-by="label"
    :label="label"
    selectedLabel=""
    selectLabel=""
    deselectLabel=""
    :limit="3"
    :max-height="200"
    @open="isOpen = true"
    @close="isOpen = false"
  >
    <!-- open-direction="bottom" -->
    <template #noResult><p class="text-center">Not Found.</p></template>
    <template #placeholder
      ><span class="pl-1.25">{{ placeholder }}</span></template
    >
    <template #caret>
      <div
        class="absolute right-2 top-1/2 -translate-y-1/2 cursor-pointer transition-transform duration-200"
        :class="{ 'rotate-180': isOpen }"
      >
        <ChevronDown size="18" color="#000" />
      </div>
    </template>
  </Multiselect>
</template>
