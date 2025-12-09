<script setup>
import { ref } from "vue";

import Header from "./components/Header.vue";
import NavModal from "./components/NavModal.vue";
import HeroView from "./components/HeroComponents/HeroView.vue";

const showModal = ref(false);

const closeModal = () => {
  showModal.value = false;
};
</script>

<template>
  <div class="w-screen">
    <Header :open="() => (showModal = true)" />

    <NavModal v-if="showModal" :close="closeModal" />

    <main>
      <HeroView />
    </main>
  </div>
</template>
