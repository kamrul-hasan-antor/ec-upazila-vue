<script setup>
import Button from "./Button.vue";
</script>

<template>
  <div
    class="relative w-full overflow-hidden bg-[url('/src/assets/images/upazila-hero-bg.png')] bg-cover bg-center flex items-center h-full min-h-80 lg:min-h-110 py-12 lg:py-0"
  >
    <div
      class="absolute inset-0 bg-linear-to-tr md:bg-linear-to-r from-black/60 md:from-black/80 via-black/60 to-black/15 pointer-events-none"
    ></div>

    <div class="container mx-auto h-full relative z-10 py-10">
      <div class="flex items-center gap-2 mb-4">
        <div class="h-1 w-10 bg-[#009951] rounded"></div>
        <p class="text-[#86EFAC]">ঢাকা বিভাগ › গাজীপুর › শ্রীপুর উপজেলা</p>
      </div>
      <h1
        class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4 sm:mb-6 leading-tight text-center lg:text-start"
      >
        <!-- <h1 class="text-white text-2xl md:text-4xl font-bold"> -->
        স্বচ্ছ ও নিরপেক্ষ নির্বাচনের মাধ্যমে<br />গণতন্ত্র সুদৃঢ়করণ
      </h1>

      <p
        class="text-white/80 leading-relaxed text-center lg:text-start text-base max-w-2xl"
      >
        বাংলাদেশ নির্বাচন কমিশন একটি স্বাধীন সাংবিধানিক প্রতিষ্ঠান যা দেশের সকল
        নির্বাচন পরিচালনা ও তত্ত্বাবধান করে।
      </p>

      <div class="mt-6 flex items-center gap-4">
        <Button class="text-sm font-normal! border-2 border-[#00814E]">
          সর্বশেষ নোটিশ দেখুন
        </Button>
        <Button
          class="text-sm font-normal! bg-white/10 border-2 border-white/30 hover:bg-white/20"
        >
          ভোটার তথ্য যাচাই করুন
        </Button>
      </div>
    </div>
  </div>
</template>
