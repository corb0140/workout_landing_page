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
  <div class="h-auto py-10 px-40 lg:flex flex-col hidden relative">
    <div class="gap-4 flex flex-col">
      <h1 class="uppercase text-9xl font-bold tracking-wider max-w-200">
        Workout with me
      </h1>

      <p class="text-sm font-light text-off-white/65 max-w-120">
        A huge selection of health and fitness content, healthy recipes and
        transformation stories to help you get fit and stay fit!
      </p>

      <button
        class="bg-orange rounded-md p-4 mt-4 text-sm self-start font-medium"
      >
        Join Club Now!
      </button>
    </div>

    <!-- HERO IMAGE & DATA -->
    <div class="mt-5 h-150 -right-[13%] w-full absolute p-5">
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
        class="flex flex-col gap-1 py-4 px-8 rounded-xl bg-[#EF8964] absolute top-[5%] left-[58%] min-w-40"
      >
        <span class="h-7.5 w-7.5 rounded-full bg-off-white/40 p-2">
          <img
            src="../../assets//images//running-stick-figure.png"
            alt=""
            class="object-contain"
          />
        </span>

        <span class="font-bold flex gap-1">
          <p class="text-2xl">{{ kmCount }}</p>
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
        class="absolute top-[60%] left-[30%] rounded-xl bg-gray py-7 pl-2 px-5 flex items-center gap-4 max-w-55"
      >
        <span class="w-5 md:w-7">
          <img
            src="../../assets//images/play-button.png"
            alt=""
            class="object-contain"
          />
        </span>

        <span class="flex flex-col gap-1">
          <p class="font-bold text-2xl">{{ videoTutorialCount }}+</p>

          <p class="text-lg opacity-70">Video Tutorial</p>
        </span>
      </motion.div>

      <!-- WORKOUT VIDEOS -->
      <motion.div
        :variants="variants"
        initial="hidden"
        animate="show"
        @animationComplete="startCount(2)"
        :custom="2"
        class="absolute bottom-[5%] right-[27%] bg-[#7A29DC] px-5 py-7 rounded-xl flex flex-col gap-2 max-w-60"
      >
        <p class="font-bold text-2xl">{{ freeWorkoutVideosCount }}+</p>

        <p class="text-lg opacity-70">Free Workout Videos</p>
      </motion.div>
    </div>

    <!-- FEATURED IN -->
    <div class="mt-35 flex flex-col gap-4 self-start py-2 px-3">
      <p class="uppercase tracking-wide opacity-65 text-sm font-semibold">
        As Featured In
      </p>

      <span class="flex gap-10 h-10 w-15">
        <motion.img
          v-for="(image, index) in featuredLogos"
          :key="index"
          :src="image"
          :variants
          initial="hidden"
          animate="show"
          :custom="index"
          alt="logo image"
          class="object-contain"
        />
      </span>
    </div>
  </div>
</template>
