<template>
  <div class="bg-[#111827] min-h-screen">
    <!--wrap components in suspense to handle loading-->
    <Suspense>
      <template #default>
        <!--wrap al comment inside a single root element-->
        <div>
          <navbar />
          <HeroSection />
          <AboutSection />
          <ExperienceAndSkills />
          <LatestProjSection />
          <ContactSection />
          <Footer />
          <BackToTop />
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <loadingSpinner/>
        </div>
      </template>
    </Suspense>
  </div>
</template>

<script setup>
import {defineAsyncComponent} from 'vue';
//import components asynchronusly
const navbar = defineAsyncComponent(()=>import('@/components/navbar.vue'));
const HeroSection = defineAsyncComponent(()=>import('@/components/HeroSection.vue'));
const AboutSection = defineAsyncComponent(()=>import('@/components/AboutSection.vue'));
const ContactSection = defineAsyncComponent(()=>import('@/components/ContactSection.vue'));
const LatestProjSection = defineAsyncComponent(()=>import('@/components/LatestProjSection.vue'));
const ExperienceAndSkills = defineAsyncComponent(()=>import('@/components/ExperienceAndSkills.vue'));
const Footer = defineAsyncComponent(()=>import('@/components/Footer.vue'));
const BackToTop = defineAsyncComponent(()=>import('@/components/BackToTop.vue'));
import loadingSpinner from './components/loadingSpinner.vue';
</script>
<style>
*{
  scrollbar-width: thin;
  scrollbar-color: #111827 #f1f1f1;
}
@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
