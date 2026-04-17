<script setup>
import Logo from "./Logo.vue";
import Button from "./Button.vue";
import { Phone } from "@lucide/vue";
</script>

<template>
  <div class="border-b border-[#ccc]">
    <div class="container">
      <div
        class="flex flex-col sm:flex-row py-2 md:items-center justify-between"
      >
        <a href="/">
          <Logo />
        </a>

        <div class="flex items-center justify-center gap-4 md:gap-6">
          <div class="flex items-center divide-x divide-[#b3b3b3]">
            <p class="text-[#333] text-sm pr-3">৫ কার্তিক, ১৪৩২</p>
            <p class="text-[#00814E] text-sm px-3 font-semibold">বাংলা</p>
            <p class="text-[#333] text-sm pl-3">English</p>
          </div>

          <!-- btton -->
          <Button variant="primary">
            <Phone class="fill-white size-4" />
            <span class="text-sm hidden md:inline">জরুরি যোগাযোগ</span>
          </Button>
        </div>
      </div>
    </div>
  </div>
</template>
