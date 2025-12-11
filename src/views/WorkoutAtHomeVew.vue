<script setup>
import "primeicons/primeicons.css";
</script>

<template>
  <div class="mt-15 py-2.5 flex flex-col px-4">
    <div class="flex flex-col gap-4">
      <h2 class="text-2xl">Workout at home for free</h2>

      <p class="text-sm opacity-65">
        We believe fitness should be accessible to everyone, everywhere,
        regardless of income or access to a gym. With hundreds of professional
        workouts, healthy recipes and informative articles, as well as one of
        the most positive communities on the web, you'll have everything you
        need to reach your personal fitness goals - for free!
      </p>

      <button class="flex gap-2 items-center">
        <p class="text-orange">See More</p>
        <span class="pi pi-arrow-right" />
      </button>
    </div>

    <div class="mt-2 rounded-xl overflow-hidden">
      <img
        src="../assets//images//woman-image-1.png"
        alt="image of woman stretching"
      />
    </div>
  </div>
</template>
