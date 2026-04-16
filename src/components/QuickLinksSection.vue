<script setup lang="ts">
import { FileText, Info, Phone, Vote } from "@lucide/vue";
import QuickLinksCards from "./QuickLinksCards.vue";
import { h } from "vue";
import SearchBox from "./SearchBox.vue";

const quickLinks = [
  {
    title: "নির্বাচন তথ্য",
    icon: () => h(Vote, { class: "text-[#374151] size-8" }),
    description: "জাতীয় ও স্থানীয় সরকার নির্বাচন সম্পর্কিত সকল তথ্য",
    color: "#FD641C",
    url: "/",
  },
  {
    title: "ভোটার নিবন্ধন",
    icon: () => h(FileText, { class: "text-[#374151] size-6.5" }),
    description: "নতুন ভোটার নিবন্ধন ও তথ্য সংশোধনের নির্দেশিকা",
    color: "#C2042E",
    url: "/results",
  },
  {
    title: "জরুরি যোগাযোগ",
    icon: () => h(Phone, { class: "text-[#374151] size-6" }),
    description: "উপজেলা নির্বাচন অফিসের ঠিকানা ও ফোন নম্বর",
    color: "#00814E",
    url: "/voter-info",
  },
];
</script>

<template>
  <div class="bg-[#F9FAFB] pb-16">
    <div class="container px-4">
      <div class="max-w-5xl mx-auto">
        <div
          class="relative z-10 -mt-12 md:-mt-16 bg-white rounded-xl shadow-[0px_8px_40px_0px_#00000025] border border-gray-100 px-6 py-5 md:px-10 md:py-7"
        >
          <h2
            class="text-base md:text-lg font-semibold text-gray-700 mb-4 border-l-4 border-[#009951] pl-3"
          >
            উপজেলা তথ্য অনুসন্ধান
          </h2>

          <SearchBox />

          <div
            class="mt-2 flex items-start sm:items-center gap-2 bg-[#F0FDF4] border-l-4 border border-[#00814E] rounded-md px-4 py-3 text-sm text-[#374151]"
          >
            <Info class="size-5 shrink-0" />
            <span class="pt-0.5"
              >আপনার অঞ্চল, জেলা, উপজেলা ও থানা নির্বাচন করুন। স্থানীয় অফিসের
              বিস্তারিত তথ্য, নোটিশ, জনসেবা এবং এলাকাভিত্তিক গুরুত্বপূর্ণ তথ্য
              দেখতে পাবেন।</span
            >
          </div>
        </div>

        <div class="grid md:grid-cols-3 gap-6 mt-10">
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
  </div>
</template>
