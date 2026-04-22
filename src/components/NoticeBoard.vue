<script setup>
import { ref, computed } from "vue";
import { ArrowRight, ChevronRight } from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import { cn } from "@/utils/cn";
import Button from "./Button.vue";
import SelectOptions from "./SelectOptions.vue";

const tabs = [
  { title: "বিজ্ঞপ্তি" },
  { title: "সংবাদ ও ঘটনাবলী" },
  { title: "সরকারি বিজ্ঞপ্তি" },
  { title: "টেন্ডার" },
];

const activeTab = ref("বিজ্ঞপ্তি");

const activeTabObject = computed({
  get: () => tabs.find((t) => t.title === activeTab.value) ?? null,
  set: (val) => {
    if (val) activeTab.value = val.title;
  },
});

const notices = [
  {
    id: 1,
    day: "২৪",
    month: "অক্টো ২০২৫",
    description:
      "আসর খাদ্য সরকার নির্বাচনের চূড়ান্ত ভোটার তালিকা প্রণতি সংক্রান্ত নির্দেশিকা। আসর খাদ্য সরকার নির্বাচনের চূড়ান্ত ভোটার তালিকা প্রণতি সংক্রান্ত নির্দেশিকা।",
  },
  {
    id: 2,
    day: "২১",
    month: "অক্টো ২০২৫",
    description:
      "চলতি মৌসুমে ড্রাগণ মুলো কৃষি সরঞ্জাম বিতরণ সংক্রান্ত কৃষকদের প্রতি বিজ্ঞপ্তি। চলতি মৌসুমে ড্রাগণ মুলো কৃষি সরঞ্জাম বিতরণ সংক্রান্ত কৃষকদের প্রতি বিজ্ঞপ্তি।",
  },
  {
    id: 3,
    day: "১৮",
    month: "অক্টো ২০২৫",
    description:
      "উপজেলা ভূমি অফিসের জমি মিউটেশন ও রেকর্ড সংশোধনের জন্য পণ-তালিকার সমস্যুতি। উপজেলা ভূমি অফিসের জমি মিউটেশন ও রেকর্ড সংশোধনের জন্য পণ-তালিকার সমস্যুতি।",
  },
  {
    id: 4,
    day: "১৫",
    month: "অক্টো ২০২৫",
    description:
      "দুর্যোগ ব্যবস্থাপনা শাখার অধীনে অস্থায়ী প্রকল্প সহকারী নিয়োগের বিজ্ঞপ্তি। দুর্যোগ ব্যবস্থাপনা শাখার অধীনে অস্থায়ী প্রকল্প সহকারী নিয়োগের বিজ্ঞপ্তি।",
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
        class="grid md:grid-cols-[250px_1fr] lg:grid-cols-[280px_1fr] xl:grid-cols-[325px_1fr] border border-[#E5E5E6] rounded-lg mt-6"
      >
        <!-- left side -->
        <div class="hidden md:block bg-[#F1F3F5] rounded-l-lg h-full overflow-y-auto">
          <ul class="flex flex-col border-r border-[#E5E5E6]">
            <li v-for="(tab, index) in tabs" :key="index">
              <button
                @click="activeTab = tab.title"
                :class="
                  cn(
                    'px-6 py-3 cursor-pointer group w-full flex justify-between items-center text-sm border-b transition-colors duration-200',
                    activeTab === tab.title
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
                    activeTab === tab.title
                      ? 'opacity-100 translate-x-0'
                      : 'opacity-0 -translate-x-1 group-hover:opacity-100 group-hover:translate-x-0'
                  "
                />
              </button>
            </li>
          </ul>
        </div>

        <div class="md:hidden cursor-pointer">
          <SelectOptions
            v-model="activeTabObject"
            :options="tabs"
            placeholder="থানা নির্বাচন করুন"
            label="title"
            :searchable="false"
          />
        </div>

        <!-- right side -->
        <div class="p-5">
          <ul class="space-y-4 divide-y divide-[#E5E5E6]">
            <li v-for="(notice, index) in notices" :key="index">
              <div
                class="flex flex-col sm:flex-row md:flex-col lg:flex-row items-start gap-2 sm:gap-4 pb-4"
              >
                <div
                  :class="
                    cn(
                      'text-sm w-18 hidden sm:flex md:hidden lg:flex flex-col items-center justify-center py-2 px-1.5 rounded-lg bg-[#F3F4F6] text-[#6B7280]',
                      index === 0 && 'bg-[#009951] text-white',
                    )
                  "
                >
                  <span class="text-lg font-semibold">
                    {{ notice.day }}
                  </span>
                  <span class="text-xs">
                    {{ notice.month }}
                  </span>
                </div>

                <p class="text-[#111827] flex-1 text-sm">
                  {{ notice.description }}
                </p>
                <div
                  class="flex justify-between items-center w-full sm:w-auto md:w-full lg:w-auto"
                >
                  <p
                    class="sm:hidden md:block lg:hidden text-xs text-[#6B7280]"
                  >
                    {{ notice.day }} {{ notice.month }}
                  </p>

                  <button
                    class="text-[#009951] text-xs flex items-center gap-2 group cursor-pointer"
                  >
                    View Details
                    <ArrowRight
                      class="size-3 -translate-x-1 group-hover:opacity-100 group-hover:translate-x-0 transition-all duration-300"
                    />
                  </button>
                </div>
              </div>
            </li>
          </ul>

          <div class="flex justify-end">
            <Button
              class="group bg-white hover:bg-white text-[#009951]! mt-4 border border-[#E5E5E6] hover:border-[#009951] text-[14px] font-normal!"
            >
              View All Notices
              <ArrowRight
                class="size-3.5 -translate-x-1 group-hover:opacity-100 group-hover:translate-x-0 transition-all duration-300"
              />
            </Button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<!--<ArrowRight />  -->
