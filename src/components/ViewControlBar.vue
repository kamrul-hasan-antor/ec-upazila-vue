<script setup>
import { Landmark } from "@lucide/vue";
</script>

<template>
  <div class="print-d-none bg-[#2C2C2C] md:h-11 flex items-center py-1">
    <div class="container flex flex-col sm:flex-row justify-between gap-2">
      <div class="flex items-center gap-2">
        <Landmark class="text-[#d5d5d5] size-4.5" />

        <p class="text-[#d5d5d5] text-xs md:text-sm">
          গণপ্রজাতন্ত্রী বাংলাদেশ সরকার
        </p>
      </div>

      <div
        class="flex justify-between items-center sm:divide-x sm:divide-[#6b6b6b]"
      >
        <p class="text-[#d5d5d5] text-xs md:text-sm pr-3">
          আজকের পরিদর্শন: ৫৮০
        </p>
        <p class="text-[#d5d5d5] text-xs md:text-sm pl-3">
          মোট পরিদর্শন: ১০২,৪৫৬
        </p>
      </div>
    </div>
  </div>
</template>
