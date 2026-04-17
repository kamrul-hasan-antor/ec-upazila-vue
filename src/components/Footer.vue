<script setup>
import logoImage from "@/assets/images/logo.png";
import { ArrowRight, Mail, MapPin, Phone } from "@lucide/vue";

const footerLinks = [
  {
    title: "দ্রুত লিংক",
    links: [
      { name: "হোম", url: "/" },
      { name: "উপজেলা পরিচিতি", url: "/" },
      { name: "নোটিশ বোর্ড", url: "/" },
      { name: "অফিস তথ্য", url: "/" },
    ],
  },
  {
    title: "গুরুত্বপূর্ণ লিংক",
    links: [
      { name: "জাতীয় তথ্য বাতায়ন", url: "/" },
      { name: "বাংলাদেশ নির্বাচন কমিশন", url: "/" },
      { name: "ফর্ম পোর্টাল", url: "/" },
      { name: "নাগরিক সনদ", url: "/" },
    ],
  },
];
</script>

<template>
  <footer class="bg-[#131313]">
    <div class="container">
      <div class="pb-8 pt-10 md:pb-12 md:pt-15">
        <div
          class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8 lg:gap-x-13"
        >
          <div class="space-y-4 sm:col-span-2 md:col-span-3 lg:col-span-1">
            <div class="flex items-center gap-3">
              <img
                :src="logoImage"
                alt="logo"
                class="w-15 h-13.5 md:w-17 md:h-15.5 md:absolute"
              />

              <p
                class="text-white text-base md:text-lg font-semibold leading-tight md:ml-20"
              >
                বাংলাদেশ নির্বাচন কমিশন
              </p>
            </div>

            <div class="space-y-2 text-sm text-[#D1D5DB] md:pt-6">
              <p class="text-white/60">
                বাংলাদেশ নির্বাচন কমিশনের উপজেলা পোর্টাল – স্থানীয় নির্বাচন
                তথ্য, অফিস যোগাযোগ এবং নাগরিক সেবার একটি কেন্দ্রীয় প্ল্যাটফর্ম।
              </p>
            </div>
          </div>

          <div v-for="item in footerLinks" :key="item.title" class="">
            <h4 class="text-white">{{ item.title }}</h4>

            <ul class="mt-5 space-y-3">
              <li v-for="link in item.links" :key="link.name">
                <a
                  :href="link.url"
                  class="text-white/60 flex items-center gap-2 text-sm hover:text-white transition-colors duration-200"
                >
                  <ArrowRight class="size-3.5 text-[#4ADE80]" />
                  {{ link.name }}
                </a>
              </li>
            </ul>
          </div>

          <div class="">
            <h4 class="text-white">সেবাসমূহ</h4>

            <ul class="mt-5 space-y-3">
              <li>
                <a
                  href="/"
                  class="text-white/60 flex items-center gap-2 text-sm hover:text-white transition-colors duration-200"
                >
                  <MapPin class="size-3.5 text-[#4ADE80]" />
                  আগারগাঁও, ঢাকা-১২০৭
                </a>
              </li>
              <li>
                <a
                  href="/"
                  class="text-white/60 flex items-center gap-2 text-sm hover:text-white transition-colors duration-200"
                >
                  <Mail class="size-3.5 text-[#4ADE80]" />
                  info@ecs.gov.bd
                </a>
              </li>
              <li>
                <a
                  href="/"
                  class="text-white/60 flex items-center gap-2 text-sm hover:text-white transition-colors duration-200"
                >
                  <Phone class="size-3.5 text-[#4ADE80]" />
                  +880 2 8124777
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div
        class="flex py-4 border-t border-[#2a2a2a] justify-between items-center"
      >
        <p class="text-sm text-white/40">
          All Rights Reserved &copy; 2026. Bangladesh Election Commission
        </p>

        <div class="flex gap-4">
          <a
            v-for="lable in ['Privacy Policy', 'Terms of Use']"
            href="/"
            class="text-sm text-white/40 hover:text-white transition-colors duration-200"
          >
            {{ lable }}
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>
