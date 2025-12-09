<script setup>
import heroImage from "@/assets/images/hero-image.png";
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
        :src="heroImage"
        alt="image of man tying laces"
        class="h-full w-full object-contain"
      />

      <!-- KM RUN -->
      <div
        class="flex flex-col gap-1 py-2 px-6 rounded-xl bg-[#EF8964] absolute top-0 right-3"
      >
        <span class="h-6.5 w-6.5 rounded-full bg-off-white/40 p-1.5">
          <img
            src="../../assets//images//running-stick-figure.png"
            alt=""
            class="object-contain"
          />
        </span>

        <span class="font-bold flex gap-1">
          <p class="text-xl">4,95</p>
          <p class="text-sm self-end relative bottom-0.5">km</p>
        </span>
      </div>

      <!-- VIDEO TUTORIALS -->
      <div
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
          <p class="font-bold text-xl">350+</p>

          <p class="text-sm opacity-70">Video Tutorial</p>
        </span>
      </div>

      <!-- WORKOUT VIDEOS -->
      <div
        class="absolute bottom-10 right-0 bg-[#7A29DC] pl-2 py-3 rounded-xl flex flex-col gap-2 max-w-30"
      >
        <p class="font-bold text-xl">500+</p>

        <p class="text-sm opacity-70">Free Workout Videos</p>
      </div>
    </div>

    <!-- FEATURED IN -->
  </div>
</template>
