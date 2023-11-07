<script setup>
import ClientsFeedbackSection from "./components/ClientsFeedbackSection.vue";
import ContactSection from "./components/ContactSection.vue";
import FooterSection from "./components/FooterSection.vue";
import HeaderSection from "./components/HeaderSection.vue"
import HowCanHelpSection from "./components/HowCanHelpSection.vue";
import IntroSection from "./components/IntroSection.vue";
import OurClientsSection from "./components/OurClientsSection.vue";
import VideoGuideSection from "./components/VideoGuideSection.vue";
</script>

<template>
  <HeaderSection />
  <main class="grid-container">
    <IntroSection />
    <OurClientsSection />
    <HowCanHelpSection />
    <!-- <VideoGuideSection />
    <ClientsFeedbackSection />
    <ContactSection /> -->
  </main>
  <!-- <FooterSection /> -->
</template>

<style scoped></style>
