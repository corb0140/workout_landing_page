<script setup>
import { ref } from "vue";
import { motion } from "motion-v";
import "primeicons/primeicons.css";

import Header from "./components/Header.vue";
import NavModal from "./components/NavModal.vue";
import HeroView from "./views/HeroViews/HeroView.vue";
import WhereToStartView from "./views/WhereToStartView.vue";
import WorkoutAtHomeVew from "./views/WorkoutAtHomeVew.vue";
import TrainingProgramView from "./views/TrainingProgramView.vue";
import MembershipView from "./views/MembershipView.vue";

const showModal = ref(false);

const closeModal = () => {
  showModal.value = false;
};

const backToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};

const scrollY = ref(0);

window.addEventListener("scroll", () => {
  scrollY.value = window.scrollY;
});
</script>

<template>
  <div class="w-screen relative pb-15">
    <Header :open="() => (showModal = true)" />

    <NavModal v-if="showModal" :close="closeModal" />

    <main>
      <HeroView />

      <motion.div
        :initial="{ opacity: 0, y: 60 }"
        :whileInView="{
          opacity: 1,
          y: 0,
          transition: { duration: 1, delay: 0.5 },
        }"
        :inViewOptions="{ once: true }"
      >
        <WhereToStartView />
      </motion.div>

      <motion.div
        :initial="{ opacity: 0, y: 60 }"
        :whileInView="{
          opacity: 1,
          y: 0,
          transition: { duration: 1, delay: 0.5 },
        }"
        :inViewOptions="{ once: true }"
      >
        <WorkoutAtHomeVew />
      </motion.div>

      <motion.div
        :initial="{ opacity: 0, y: 60 }"
        :whileInView="{
          opacity: 1,
          y: 0,
          transition: { duration: 1, delay: 0.5 },
        }"
        :inViewOptions="{ once: true }"
      >
        <TrainingProgramView />
      </motion.div>

      <motion.div
        :initial="{ opacity: 0, y: 60 }"
        :whileInView="{
          opacity: 1,
          y: 0,
          transition: { duration: 1, delay: 0.5 },
        }"
        :inViewOptions="{ once: true }"
      >
        <MembershipView />
      </motion.div>
    </main>

    <button
      @click="backToTop"
      class="fixed bottom-4 right-5 p-2.5 rounded-md bg-orange items-center flex gap-1"
      :class="scrollY > 768 ? 'block' : 'hidden'"
    >
      Back to Top
      <span class="pi pi-chevron-right" />
    </button>
  </div>
</template>
