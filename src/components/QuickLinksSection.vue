<script setup lang="ts">
import { Info, Vote } from "@lucide/vue";
import QuickLinksCards from "./QuickLinksCards.vue";

const quickLinks = [
  {
    title: "নির্বাচন তথ্য",
    icon: Vote,
    description: "বিস্তারিত তথ্য",
    color: "#009951",
    url: "/",
  },
  {
    title: "নির্বাচন ফলাফল",
    icon: Vote,
    description: "বিস্তারিত ফলাফল",
    color: "#FF5733",
    url: "/results",
  },
  {
    title: "ভোটার তথ্য",
    icon: Vote,
    description: "ভোটার তথ্য",
    color: "#337AFF",
    url: "/voter-info",
  },
];
</script>

<template>
  <div class="bg-[#F9FAFB] pb-16">
    <div class="container px-4">
      <!-- Overlapping Card -->
      <div
        class="relative z-10 -mt-12 md:-mt-16 bg-white rounded-xl shadow-[0px_8px_40px_0px_#00000025] border border-gray-100 px-6 py-5 md:px-10 md:py-7"
      >
        <h2
          class="text-base md:text-lg font-semibold text-gray-700 mb-4 border-l-4 border-[#009951] pl-3"
        >
          উপজেলা তথ্য অনুসন্ধান
        </h2>

        <!-- Info note -->
        <div
          class="mt-2 flex items-start gap-2 bg-green-50 border border-green-200 rounded-md px-4 py-3 text-sm text-green-800"
        >
          <Info />
          <span
            >অনুগ্রহ করে বিভাগ, জেলা, উপজেলা এবং কেন্দ্র নির্বাচন করুন। সঠিক
            তথ্য নির্বাচন করলে আপনি প্রয়োজনীয় তথ্য পাবেন।</span
          >
        </div>
      </div>

      <!-- Quick Links -->
      <div class="grid md:grid-cols-3 gap-4 mt-10">
        <QuickLinksCards
          v-for="link in quickLinks"
          :key="link.title"
          :title="link.title"
          :description="link.description"
          :color="link.color"
          :url="link.url"
          :icon="link.icon"
        />
      </div>
    </div>
  </div>
</template>
