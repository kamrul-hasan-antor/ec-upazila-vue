<script setup>
import {
  Hospital,
  Building,
  Shield,
  GraduationCap,
  Leaf,
  BusFront,
} from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import { h } from "vue";

const upazilaInfo = [
  {
    title: "৪৬৫.২ বর্গ কি.মি.",
    description: "আয়তন",
  },
  {
    title: "৮টি",
    description: "ইউনিয়ন",
  },
  {
    title: "৪৬৫.২ বর্গ কি.মি.",
    description: "আয়তন",
  },
  {
    title: "৮টি",
    description: "ইউনিয়ন",
  },
];

const administrativeInfo = [
  {
    title: "স্থানীয় সরকার অফিস",
    description: "উপজেলা পরিষদ কমপ্লেক্স, শ্রীপুর",
    icon: () => h(Building),
  },
  {
    title: "প্রধান হাসপাতাল",
    description: "শ্রীপুর উপজেলা স্বাস্থ্য কমপ্লেক্স (৫০ শয্যা)",
    icon: () => h(Hospital),
  },
  {
    title: "পুলিশ স্টেশন",
    description: "শ্রীপুর মডেল থানা",
    icon: () => h(Shield),
  },
  {
    title: "শিক্ষা প্রতিষ্ঠান",
    description: "১২টি কলেজ, ৪৫টি উচ্চ বিদ্যালয়",
    icon: () => h(GraduationCap),
  },
  {
    title: "সংযোগ",
    description: "ঢাকা-ময়মনসিংহ মহাসড়ক, শ্রীপুর রেলওয়ে সেন্ট",
    icon: () => h(BusFront),
  },
  {
    title: "কৃষি",
    description: "ধান, পাট, কাঁঠাল, পোল্ট্রি হাব",
    icon: () => h(Leaf),
  },
];
</script>

<template>
  <div class="section-gap">
    <div class="container">
      <SectionTitle
        title="উপজেলা সংক্ষিপ্ত বিবরণের – আমার পরিচয়"
        description="আপনার ফিল্টার নির্বাচনের উপর ভিত্তি করে তথ্যের প্রদর্শন পরিবর্তিত হয়।"
      />

      <div
        class="grid xl:grid-cols-3 mt-6 rounded-xl border border-[#EBEBEB] gap-4"
      >
        <div class="col-span-1">
          <div
            class="rounded-t-xl xl:rounded-tr-none xl:rounded-l-xl bg-[#009951] p-5"
          >
            <p>Dhaka Division</p>

            <h2 class="text-2xl font-bold text-white mt-4">Sreepur Upazila</h2>
            <p class="text-sm text-[#e5f5ed] mt-4">
              শ্রীপুর উপজেলা নির্বাচন অফিস বাংলাদেশ নির্বাচন কমিশনের একটি
              গুরুত্বপূর্ণ আঞ্চলিক কার্যালয়। এখানে উপজেলার সকল নির্বাচনী
              কার্যক্রম, ভোটার তালিকা প্রস্তুত ও হালনাগাদ, রাজনৈতিক দলের নিবন্ধন
              সংক্রান্ত তথ্য এবং ভোটকেন্দ্র ব্যবস্থাপনার কাজ পরিচালিত হয়।
            </p>

            <div
              class="grid sm:grid-cols-2 md:grid-cols-4 xl:grid-cols-2 gap-4 mt-4"
            >
              <div
                v-for="(info, index) in upazilaInfo"
                :key="index"
                class="bg-[#e5f5ed] rounded-lg p-3 text-center"
              >
                <h3 class="text-lg font-semibold mb-1 text-[#15803D]">
                  {{ info.title }}
                </h3>
                <p class="text-sm text-[#374A41]">{{ info.description }}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="xl:col-span-2">
          <div class="p-5">
            <p
              class="text-[#0F172A] text-lg font-semibold border-b border-[#EBEBEB] pb-2.5"
            >
              মূল প্রশাসনিক বিবরণ
            </p>

            <div
              class="grid sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-2 gap-y-6 sm:gap-y-12 gap-x-4 mt-5"
            >
              <div v-for="(info, index) in administrativeInfo" :key="index">
                <div class="flex items-center gap-2 mb-3">
                  <component :is="info.icon" class="size-4 text-[#6B7280]" />
                  <p class="font-semibold text-[#6B7280] text-sm">
                    {{ info.title }}
                  </p>
                </div>
                <p class="text-[#0F172A] font-semibold">
                  {{ info.description }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
