

<script setup>
import { ref, watch } from "vue";

import SelectOptions from "./SelectOptions.vue";
import Button from "./Button.vue";

const anchal = ref(null);
const zila = ref(null);
const upazila = ref(null);
const thana = ref(null);

const anchalOptions = [
  { name: "ঢাকা" },
  { name: "চট্টগ্রাম" },
  { name: "খুলনা" },
  { name: "রাজশাহী" },
];

const zilaOptions = [
  { name: "ঢাকা" },
  { name: "ফরিদপুর" },
  { name: "চট্টগ্রাম" },
  { name: "কক্সবাজার" },
];

const upazilaOptions = [
  { name: "সাভার" },
  { name: "দোহার" },
  { name: "ভাঙ্গা" },
  { name: "বোয়ালখালী" },
];

const thanaOptions = [
  { name: "সাভার থানা" },
  { name: "দোহার থানা" },
  { name: "ভাঙ্গা থানা" },
  { name: "বোয়ালখালী থানা" },
];

// watch(anchal, (val) => console.log("অঞ্চল:", val));
// watch(zila, (val) => console.log("জেলা:", val));
// watch(upazila, (val) => console.log("উপজেলা:", val));
// watch(thana, (val) => console.log("থানা:", val));
</script>

<template>
  <div
    class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-[1fr_1fr_1fr_1fr_0.4fr] gap-4"
  >
    <div>
      <p class="text-[#00814E] text-base mb-2">অঞ্চল</p>

      <SelectOptions
        v-model="anchal"
        :options="anchalOptions"
        placeholder="অঞ্চল নির্বাচন করুন"
        label="name"
      />
    </div>

    <div>
      <p class="text-[#00814E] text-base mb-2">জেলা</p>

      <SelectOptions
        v-model="zila"
        :options="zilaOptions"
        placeholder="জেলা নির্বাচন করুন"
        label="name"
      />
    </div>

    <div>
      <p class="text-[#00814E] text-base mb-2">উপজেলা</p>

      <SelectOptions
        v-model="upazila"
        :options="upazilaOptions"
        placeholder="উপজেলা নির্বাচন করুন"
        label="name"
      />
    </div>

    <div>
      <p class="text-[#00814E] text-base mb-2">থানা</p>

      <SelectOptions
        v-model="thana"
        :options="thanaOptions"
        placeholder="থানা নির্বাচন করুন"
        label="name"
      />
    </div>

    <div
      class="flex items-end justify-end md:justify-start sm:col-span-2 md:col-span-1"
    >
      <Button class="text-sm font-normal! h-10 w-full sm:w-max">
        অনুসন্ধান
      </Button>
    </div>
  </div>
</template>
