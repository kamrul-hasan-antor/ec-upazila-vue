<script setup>
import { h } from "vue";
import {
  FileText,
  Building2,
  PhoneCall,
  BarChart2,
  Landmark,
  MessageSquare,
  BookOpen,
  Download,
  BookMarked,
} from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import InfoAccessCards from "./InfoAccessCards.vue";

const cards = [
  {
    title: "ভূমি রেটিন",
    description: "উপজেলা-ভিত্তিক জমির মালিক, দলিল ও রেকর্ড সম্পর্কিত তথ্য এবং জরুরি সম্পদ সংগ্রহ করুন",
    color: "#009951",
    icon: () => h(FileText, { class: "w-5 h-5" }),
  },
  {
    title: "অফিস যোগাযোগ",
    description: "অফিসের ঠিকানা, ফোন নম্বর ও যোগাযোগের মাধ্যম সম্পর্কিত তথ্য সমূহ",
    color: "#0891B2",
    icon: () => h(Building2, { class: "w-5 h-5" }),
  },
  {
    title: "জরুরি যোগাযোগ",
    description: "জরুরি পরিস্থিতিতে, প্রশাসন ও স্বাস্থ্য সেবার প্রয়োজনীয় যোগাযোগ নম্বর",
    color: "#DC2626",
    icon: () => h(PhoneCall, { class: "w-5 h-5" }),
  },
  {
    title: "উপজেলা প্রজেটিন",
    description: "উপজেলার প্রশাসনিক, জনসংখ্যাতাত্ত্বিক ও ভৌগোলিক পরিচিতি",
    color: "#EA580C",
    icon: () => h(BarChart2, { class: "w-5 h-5" }),
  },
  {
    title: "জনসেবা",
    description: "সরকারি সেবা, পরিষেবা প্রদান ও নাগরিক সুবিধার সম্পূর্ণ বিবরণ",
    color: "#0D9488",
    icon: () => h(Landmark, { class: "w-5 h-5" }),
  },
  {
    title: "অভিযোগ ও আবেদন",
    description: "অভিযোগ দায়ের এবং সরকারি সেবার জন্য অনলাইনে আবেদন প্রক্রিয়া জানুন",
    color: "#7C3AED",
    icon: () => h(MessageSquare, { class: "w-5 h-5" }),
  },
  {
    title: "পরিচিতি ও অবস্থান",
    description: "বিভিন্ন উপজেলার পরিচিতি, বিবরণ এবং অবস্থান সম্পর্কিত তথ্য দেখুন",
    color: "#D97706",
    icon: () => h(BookOpen, { class: "w-5 h-5" }),
  },
  {
    title: "ডাউনলোড ও ফর্ম",
    description: "প্রয়োজনীয় সরকারি ফর্ম ও নথি বিনামূল্যে ডাউনলোড করুন",
    color: "#16A34A",
    icon: () => h(Download, { class: "w-5 h-5" }),
  },
  {
    title: "তথ্যসূত্র নিবন্ধ",
    description: "বিভিন্ন বিষয়ে বিস্তারিত তথ্যসূত্র, নিবন্ধ ও অনুসন্ধান করুন",
    color: "#0891B2",
    icon: () => h(BookMarked, { class: "w-5 h-5" }),
  },
];
</script>

<template>
  <div class="bg-[#F7FAFC] py-8 md:py-16">
    <div class="container">
      <SectionTitle
        title="দ্রুত তথ্য অ্যাক্সেস"
        description="পোর্টালের মূল অংশ এবং অপরিহার্য প্রশাসনিক মডিউলগুলো অন্বেষণ করুন।"
      />

      <div class="grid sm:grid-cols-2 md:grid-cols-3 gap-6 mt-8">
        <InfoAccessCards
          v-for="card in cards"
          :key="card.title"
          :title="card.title"
          :description="card.description"
          :color="card.color"
          :icon="card.icon"
        />
      </div>
    </div>
  </div>
</template>
