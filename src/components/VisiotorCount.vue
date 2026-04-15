<script setup>
import { Landmark } from "@lucide/vue";
</script>

<template>
  <div className="print-d-none bg-[#2C2C2C] md:h-11 flex items-center py-1">
    <div
      className="container flex flex-col md:flex-row justify-between"
    >
      <div className="flex items-center gap-2">
        <Landmark class="text-[#d5d5d5] size-4.5" />

        <p className="text-[#d5d5d5] text-xs md:text-sm">
          গণপ্রজাতন্ত্রী বাংলাদেশ সরকার
        </p>
      </div>

      <!-- <div className="md:h-8 flex justify-center items-center gap-4">
        <p className="text-yellow-400 text-[14px] leading-tight">efg</p>
      </div> -->

      <div class="flex justify-between items-center divide-x divide-[#6b6b6b]">
        <p className="text-[#d5d5d5] text-xs md:text-sm pr-3">
          আজকের পরিদর্শন: ৫৮০
        </p>
        <p className="text-[#d5d5d5] text-xs md:text-sm pl-3">
          মোট পরিদর্শন: ১০২,৪৫৬
        </p>
      </div>
    </div>
  </div>
</template>
