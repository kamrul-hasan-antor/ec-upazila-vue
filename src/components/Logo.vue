<script setup>
import logoImage from "@/assets/images/logo.png";
</script>

<template>
  <div className="flex items-center gap-2 md:gap-4">
    <div className="relative w-15 h-13.5 md:w-17 md:h-15.5">
      <img
        :src="logoImage"
        alt="Logo"
        className="w-full h-full object-contain"
      />
    </div>

    <div>
      <p
        className="text-[#00814E] text-lg lg:text-2xl font-semibold pt-1 font-nikosh"
      >
        বাংলাদেশ নির্বাচন কমিশন
      </p>
      <p className="text-[#F40224] text-[12px] md:text-[14px] font-nikosh">
        Bangladesh Election Commission
      </p>
    </div>
  </div>
</template>
