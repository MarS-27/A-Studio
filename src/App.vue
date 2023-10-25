<script setup>
import ClientsFeedbackSection from "./components/ClientsFeedbackSection.vue";
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
    <VideoGuideSection />
    <ClientsFeedbackSection />
  </main>
</template>

<style scoped></style>
