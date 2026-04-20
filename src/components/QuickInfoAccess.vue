<script setup>
import { h } from "vue";
import {
  FileText,
  Building2,
  PhoneCall,
  Landmark,
  MessageSquare,
  Briefcase,
  Download,
  Link2,
  Map,
} from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import InfoAccessCards from "./InfoAccessCards.vue";

const cards = [
  {
    title: "স্থানীয় নোটিশ",
    description:
      "উপজেলা কার্যালয়গুলো থেকে সকল সার্কুলার, আদেশ ও ঘোষণা সংগ্রহ করুন",
    color: "#009951",
    icon: () => h(FileText),
  },
  {
    title: "অফিস যোগাযোগ",
    description:
      "স্থানীয় প্রশাসনিক কর্মকর্তাদের ফোন নম্বর, ইমেল এবং বিস্তারিত তথ্য খুঁজুন",
    color: "#00814E",
    icon: () => h(Building2),
  },
  {
    title: "জরুরি যোগাযোগ",
    description: "পুলিশ, দমকল বাহিনী, হাসপাতাল এবং দুর্যোগ ব্যবস্থাপনা হটলাইন",
    color: "#C2042E",
    icon: () => h(PhoneCall),
  },
  {
    title: "উপজেলা প্রোফাইল",
    description: "এলাকাটির ভৌগোলিক, জনসংখ্যাতাত্ত্বিক ও ঐতিহাসিক প্রেক্ষাপট",
    color: "#FD641C",
    icon: () => h(Landmark),
  },
  {
    title: "জনসেবা",
    description: "নাগরিক পরিষেবার সংক্রান্ত তথ্য এবং আবেদন পদ্ধতি",
    color: "#1E9ABD",
    icon: () => h(Briefcase),
  },
  {
    title: "অভিযোগ ও মতামত",
    description:
      "অভিযোগ সরাসরি উপজেলা নির্বাহী কর্মকর্তার (ইউএনও) কাছে জমা দিন",
    color: "#8769DC",
    icon: () => h(MessageSquare),
  },
  {
    title: "মানচিত্র ও অবস্থান",
    description:
      "বিস্তারিত উপজেলা মানচিত্র, ইউনিয়ন সীমানা এবং অফিসের অবস্থান দেখুন",
    color: "#83144D",
    icon: () => h(Map),
  },
  {
    title: "ডাউনলোড ও ফর্ম",
    description: "সরকারি ফর্ম, নাগরিক সনদ এবং নির্দেশিকা নথি ডাউনলোড করুন",
    color: "#0369A1",
    icon: () => h(Download, { class: "w-5 h-5" }),
  },
  {
    title: "গুরুত্বপূর্ণ লিংক",
    description: "জাতীয় পোর্টাল, মন্ত্রণালয় ও অধিদপ্তরসমূহের দ্রুত লিংক",
    color: "#059669",
    icon: () => h(Link2, { class: "w-5 h-5" }),
  },
];
</script>

<template>
  <div class="bg-[#F7FAFC] section-gap">
    <div class="container">
      <SectionTitle
        title="দ্রুত তথ্য অ্যাক্সেস"
        description="পোর্টালের মূল অংশ এবং অপরিহার্য প্রশাসনিক মডিউলগুলো অন্বেষণ করুন।"
      />

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 lg:gap-6 mt-8">
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
