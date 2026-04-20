<script setup lang="ts">
import { Headset } from "@lucide/vue";
import SectionTitle from "./SectionTitle.vue";
import Button from "./Button.vue";
</script>

<template>
  <div class="section-gap">
    <div class="container">
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-x-6 gap-y-12">
        <div class="lg:col-span-2">
          <SectionTitle title="মানচিত্র" />

          <div class="mt-6">
            <iframe
              loading="lazy"
              allowFullScreen=""
              referrerPolicy="no-referrer-when-downgrade"
              src="https://www.google.com/maps?q=Bangladesh&z=6&output=embed"
              class="w-full h-100 rounded-lg border-2 border-black/20"
            >
            </iframe>
          </div>
        </div>
        <div>
          <SectionTitle title="নাগরিক সমর্থন" />

          <div
            class="mt-6 md:h-100 rounded-lg border border-[#EBEBEB] py-8 px-5 md:p-5"
          >
            <div class="flex flex-col justify-center items-center h-full">
              <div
                class="rounded-full size-16 flex items-center justify-center shrink-0 bg-[#FEF2F2]"
              >
                <Headset class="size-8 text-[#E53935]" />
              </div>

              <p class="mt-4 text-[#0F172A] text-lg font-semibold">
                সাহায্যের প্রয়োজন?
              </p>
              <p class="text-[#6B7280] text-sm text-center mt-4">
                আপনার অভিযোগ, জিজ্ঞাসা বা মতামত সরাসরি প্রশাসনের কাছে জমা দিন।
                আমরা ৩ কার্যদিবসের মধ্যে উত্তর দেওয়ার চেষ্টা করি।
              </p>

              <Button class="mt-8 w-full rounded-lg">
                <span>
                  <span class="text-2xl font-semibold">999</span>
                  <br />
                  <span class="text-sm font-normal">কল করুন</span>
                </span>
              </Button>

              <p class="text-[#6B7280] text-sm text-center mt-4">
                অথবা জাতীয় হেল্পডেস্কে ফোন করুন:
                <span class="font-semibold text-[#0F172A]">333</span>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<!--<Headphones />  -->
