<script setup>
import "primeicons/primeicons.css";

const data = [
  {
    title: "Workout Videos",
    description: "Access to hundreds of free, full-length workout videos.",
  },
  {
    title: "Workout Programs",
    description: "Affordable and effective workout programs.",
  },
  {
    title: "Meals Plans",
    description: "Plans built with registered dietitians and nutritionists.",
  },
  {
    title: "WO Plus All Access",
    description: "Add powerful features to your membership.",
  },
];
</script>

<template>
  <div class="mt-15 py-2.5 pl-4 flex flex-col gap-4">
    <h2 class="text-2xl">Not sure where to start?</h2>

    <p class="opacity-65 text-sm">
      Programs offer day-to-day guidance on an interactive calendar to keep you
      on track.
    </p>

    <div class="flex gap-3 overflow-hidden overflow-x-scroll no-scrollbar pr-4">
      <div
        v-for="(item, index) in data"
        :key="index"
        class="bg-dark-slate-blue p-5 rounded-xl flex flex-col justify-center gap-3 min-w-[304px] min-h-[190px]"
      >
        <h3 class="text-xl">{{ item.title }}</h3>

        <div class="flex gap-2 items-end">
          <p class="text-sm opacity-65">{{ item.description }}</p>
          <span class="pi pi-arrow-right" />
        </div>
      </div>
    </div>
  </div>
</template>
