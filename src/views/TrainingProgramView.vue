<script setup>
import "primeicons/primeicons.css";
</script>

<template>
  <div
    class="mt-15 py-2.5 lg:py-10 flex flex-col lg:flex-row-reverse px-8 md:px-15 lg:px-40"
  >
    <div class="flex flex-col gap-4 lg:gap-6 lg:justify-center lg:max-w-180">
      <h2 class="text-2xl md:text-4xl lg:text-5xl lg:pl-20">
        Get more with low-cost training programs and advanced features.
      </h2>

      <p class="text-sm md:text-[16px] lg:text-sm opacity-65 lg:pl-20">
        We believe fitness should be accessible to everyone, everywhere,
        regardless of income or access to a gym. With hundreds of professional
        workouts, healthy recipes and informative articles, as well as one of
        the most positive communities on the web, you'll have everything you
        need to reach your personal fitness goals - for free!
      </p>

      <button class="flex gap-2 items-center lg:pl-20">
        <p class="text-orange md:text-lg lg:text-sm">See More</p>
        <span class="pi pi-arrow-right" />
      </button>
    </div>

    <div class="mt-2 rounded-xl overflow-hidden lg:grow">
      <img
        src="../assets//images//woman-image-2.png"
        alt="image of woman stretching"
        class="h-full w-full object-contain"
      />
    </div>
  </div>
</template>
