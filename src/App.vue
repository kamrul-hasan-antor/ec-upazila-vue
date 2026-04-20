<script setup>
import Hero from "@/components/Hero.vue";
import ViewControlBar from "@/components/ViewControlBar.vue";
import HeaderSection from "@/components/HeaderSection.vue";
import QuickLinksSection from "@/components/QuickLinksSection.vue";
import SocialMedia from "@/components/SocialMedia.vue";
import Footer from "@/components/Footer.vue";
import UpazilaHeroSection from "./components/UpazilaHeroSection.vue";
import NoticeBoard from "./components/NoticeBoard.vue";
import QuickInfoAccess from "./components/QuickInfoAccess.vue";
import AboutUpazila from "./components/AboutUpazila.vue";
import LocationMap from "./components/LocationMap.vue";
</script>

<template>
  <!-- landing page start -->

  <!-- <ViewControlBar />
  <HeaderSection />
  <Hero />
  <QuickLinksSection />
  <SocialMedia />
  <Footer /> -->

  <!-- landing page end -->

  <!-- Upozila Home page start -->
  <ViewControlBar />
  <HeaderSection />
  <UpazilaHeroSection />
  <NoticeBoard />
  <QuickInfoAccess />
  <AboutUpazila />
  <LocationMap />
  <Footer></Footer>
</template>
