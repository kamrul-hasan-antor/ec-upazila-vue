<script setup>
import { ref } from "vue";
import { ChevronRight } from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import { cn } from "@/utils/cn";

const tabs = [
  { title: "বিজ্ঞপ্তি" },
  { title: "সংবাদ ও ঘটনাবলী" },
  { title: "সরকারি বিজ্ঞপ্তি" },
  { title: "টেন্ডার" },
];

const activeTab = ref(0);

const notices = [
  {
    date: "২৪ অক্টোবর ২০২৫",
    description:
      "আসর খাদ্য সরকার নির্বাচনের চূড়ান্ত ভোটার তালিকা প্রণতি সংক্রান্ত নির্দেশিকা। আসর খাদ্য সরকার নির্বাচনের চূড়ান্ত ভোটার তালিকা প্রণতি সংক্রান্ত নির্দেশিকা",
  },
  {
    date: "২১ অক্টোবর ২০২৫",
    description:
      "চলতি মৌসুমে ড্রাগণ মুলো কৃষি সরঞ্জাম বিতরণ সংক্রান্ত কৃষকদের প্রতি বিজ্ঞপ্তি। চলতি মৌসুমে ড্রাগণ মুলো কৃষি সরঞ্জাম বিতরণ সংক্রান্ত কৃষকদের প্রতি বিজ্ঞপ্তি",
  },
  {
    date: "১৮ অক্টোবর ২০২৫",
    description:
      "উপজেলা ভূমি অফিসের জমি মিউটেশন ও রেকর্ড সংশোধনের জন্য পণ-তালিকার সমস্যুতি। উপজেলা ভূমি অফিসের জমি মিউটেশন ও রেকর্ড সংশোধনের জন্য পণ-তালিকার সমস্যুতি",
  },
  {
    date: "১৫ অক্টোবর ২০২৫",
    description:
      "দুর্যোগ ব্যবস্থাপনা শাখার অধীনে অস্থায়ী প্রকল্প সহকারী নিয়োগের বিজ্ঞপ্তি। দুর্যোগ ব্যবস্থাপনা শাখার অধীনে অস্থায়ী প্রকল্প সহকারী নিয়োগের বিজ্ঞপ্তি",
  },
];
</script>

<template>
  <div class="section-gap">
    <div class="container">
      <SectionTitle
        title="নোটিশ বোর্ড"
        description="সকল প্রশাসনিক কার্যালয় থেকে সাম্প্রতিক হালনাগাদ, বিজ্ঞপ্তি ও ঘোষণা।"
      />

      <div
        class="grid grid-cols-[325px_1fr] border border-[#E5E5E6] rounded-lg mt-6"
      >
        <div class="bg-[#F1F3F5] rounded-l-lg max-h-100 overflow-y-auto">
          <ul class="flex flex-col border-r border-[#E5E5E6]">
            <li v-for="(tab, index) in tabs" :key="index">
              <button
                @click="activeTab = index"
                :class="
                  cn(
                    'px-6 py-3 cursor-pointer group w-full flex justify-between items-center text-sm border-b transition-colors duration-200',
                    activeTab === index
                      ? 'bg-white border-l-4 border-[#15803D] font-medium text-[#15803D]'
                      : 'border-l-4 border-transparent hover:bg-[#E5E5E6] text-gray-700',
                    index === 0 && 'rounded-tl-lg',
                  )
                "
              >
                {{ tab.title }}
                <ChevronRight
                  class="size-4 text-[#15803D] transition-all duration-300"
                  :class="
                    activeTab === index
                      ? 'opacity-100 translate-x-0'
                      : 'opacity-0 -translate-x-1 group-hover:opacity-100 group-hover:translate-x-0'
                  "
                />
              </button>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<!--<ArrowRight />  -->
