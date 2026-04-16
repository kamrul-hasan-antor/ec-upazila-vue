<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>

<!-- <style>
.multiselect__option--highlight {
  background: #6b7280 !important;
  color: white !important;
}

.multiselect__option--highlight::after {
  background: #6b7280 !important;
  content: "" !important;
}

.multiselect__option--selected.multiselect__option--highlight::after {
  content: "" !important;
}

.multiselect--active .multiselect__placeholder {
  color: #16a34a !important;
}

.multiselect--active .multiselect__tags {
  border-color: #3b82f6 !important;
  box-shadow: 0 0 0 2px rgba(59, 130, 246, 0.3) !important;
}

/* Hide the caret/arrow since it's always open */
.multiselect__select {
  display: none;
}

/* Always show dropdown */
.multiselect__content-wrapper {
  display: block !important;
}
</style> -->

<style>
.multiselect__input::placeholder {
  color: #adadad;
  font-size: 14px;
}
</style>

<script>
import { ChevronDown } from "@lucide/vue";
import Multiselect from "vue-multiselect";

export default {
  components: { Multiselect, ChevronDown },
  data() {
    return {
      isOpen: false,
      value: null,
      options: [
        { name: "Vue.js", language: "JavaScript" },
        { name: "Rails", language: "Ruby" },
        { name: "Laravel", language: "PHP" },
        { name: "Phoenix", language: "Elixir" },
      ],
    };
  },
};
</script>

<template>
  <div class="grid grid-cols-4">
    <multiselect
      ref="multiselect"
      v-model="value"
      :options="options"
      placeholder="অঞ্চল নির্বাচন করুন"
      track-by="name"
      label="language"
      selectedLabel=""
      selectLabel=""
      :max-height="150"
      @open="isOpen = true"
      @close="isOpen = false"
    >
      <template #noResult>
        <p class="text-center">Not Found.</p>
      </template>

      <template #placeholder>
        <span class="pl-1.25">অঞ্চল নির্বাচন করুন</span>
      </template>

      <template #caret>
        <div
          class="absolute right-2 top-1/2 -translate-y-1/2 cursor-pointer transition-transform duration-200"
          :class="{ 'rotate-180': isOpen }"
        >
          <ChevronDown size="18" color="#000" />
        </div>
      </template>
    </multiselect>
  </div>

  <div></div>
</template>
