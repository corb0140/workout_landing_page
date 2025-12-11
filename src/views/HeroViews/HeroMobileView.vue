<script setup>
import { ref } from "vue";
import { motion, animate } from "motion-v";

let kmCount = ref(0);
let videoTutorialCount = ref(0);
let freeWorkoutVideosCount = ref(0);

const targets = [4.95, 350, 500];
const countStarted = ref([false, false, false]);

import nike from "@/assets/images/nike-logo.png";
import buzzfeed from "@/assets/images/buzzfeed-logo.png";
import espirit from "@/assets/images/espirit-logo.png";
import ng from "@/assets/images/ng-logo.png";
import dw from "@/assets/images/dw-logo.png";
import huffpost from "@/assets/images/huffpost-logo.png";

const featuredLogos = [nike, buzzfeed, espirit, ng, dw, huffpost];

const startCount = (index) => {
  if (countStarted.value[index]) return;
  countStarted.value[index] = true;

  animate(0, targets[index], {
    duration: 1,
    onUpdate(v) {
      if (index === 0) kmCount.value = Number(v.toFixed(2));
      if (index === 1) videoTutorialCount.value = Math.floor(v);
      if (index === 2) freeWorkoutVideosCount.value = Math.floor(v);
    },
  });
};

const variants = {
  hidden: { opacity: 0, scale: 0 },
  show: (item) => ({
    opacity: 1,
    scale: 1,
    transition: {
      duration: 0.8,
      delay: item * 0.2,
      ease: "easeOut",
    },
  }),
};
</script>

<template>
  <div class="h-auto px-2 py-8 flex flex-col items-center lg:hidden">
    <div class="gap-4 flex flex-col max-w-90">
      <h1 class="uppercase text-center">Workout with me</h1>

      <p class="text-sm font-light text-off-white/40 text-center">
        A huge selection of health and fitness content, healthy recipes and
        transformation stories to help you get fit and stay fit!
      </p>

      <button
        class="bg-orange rounded-md p-3 mt-4 text-sm self-center font-medium"
      >
        Join Club Now!
      </button>
    </div>

    <!-- HERO IMAGE & DATA -->
    <div class="mt-15 h-100 w-full relative p-5">
      <img
        src="../../assets/images/hero-image.png"
        alt="image of man tying laces"
        class="h-full w-full object-contain"
      />

      <!-- KM RUN -->
      <motion.div
        :variants="variants"
        initial="hidden"
        animate="show"
        @animationComplete="startCount(0)"
        :custom="0"
        class="flex flex-col gap-1 py-2 px-6 rounded-xl bg-[#EF8964] absolute top-0 right-3 min-w-30"
      >
        <span class="h-6.5 w-6.5 rounded-full bg-off-white/40 p-1.5">
          <img
            src="../../assets//images//running-stick-figure.png"
            alt=""
            class="object-contain"
          />
        </span>

        <span class="font-bold flex gap-1">
          <p class="text-xl">{{ kmCount }}</p>
          <p class="text-sm self-end relative bottom-0.5">km</p>
        </span>
      </motion.div>

      <!-- VIDEO TUTORIALS -->
      <motion.div
        :variants="variants"
        initial="hidden"
        animate="show"
        @animationComplete="startCount(1)"
        :custom="1"
        class="absolute top-1/2 left-2 rounded-xl bg-gray py-3 pl-2 flex items-center gap-2 max-w-30"
      >
        <span class="w-5">
          <img
            src="../../assets//images/play-button.png"
            alt=""
            class="object-contain"
          />
        </span>

        <span class="flex flex-col gap-1">
          <p class="font-bold text-xl">{{ videoTutorialCount }}+</p>

          <p class="text-sm opacity-70">Video Tutorial</p>
        </span>
      </motion.div>

      <!-- WORKOUT VIDEOS -->
      <motion.div
        :variants="variants"
        initial="hidden"
        animate="show"
        @animationComplete="startCount(2)"
        :custom="2"
        class="absolute bottom-10 right-0 bg-[#7A29DC] pl-2 py-3 rounded-xl flex flex-col gap-2 max-w-30"
      >
        <p class="font-bold text-xl">{{ freeWorkoutVideosCount }}+</p>

        <p class="text-sm opacity-70">Free Workout Videos</p>
      </motion.div>
    </div>

    <!-- FEATURED IN -->
    <div class="mt-10 w-full flex flex-col gap-4 self-start py-2 px-3">
      <p class="uppercase tracking-wide opacity-65 text-sm font-semibold">
        As Featured In
      </p>

      <span class="flex justify-between">
        <motion.img
          v-for="(image, index) in featuredLogos"
          :key="index"
          :src="image"
          :variants
          initial="hidden"
          animate="show"
          :custom="index"
          alt="logo image"
          class="h-10 w-10 object-contain"
        />
      </span>
    </div>
  </div>
</template>
