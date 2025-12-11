<script setup>
const menubars = [1, 2, 3];

defineProps({
  open: Function,
});

const links = [
  "Workouts",
  "Programs",
  "Healthy Living",
  "Community",
  "About",
  "Store",
];
</script>

<template>
  <div
    id="nav"
    class="h-10 py-6 lg:py-8 px-5 flex justify-between items-center bg-black relative z-20"
  >
    <h1 class="uppercase text-lg">Workout</h1>

    <div
      id="hamburger-menu-icon"
      class="flex flex-col items-center justify-center gap-1 h-5 w-5 lg:hidden"
      @click="open"
    >
      <div
        id="hamburger-menu-icon"
        class="flex flex-col gap-1 h-0.5 w-5 bg-off-white rounded-sm"
        v-for="(_, index) in menubars"
        :key="index"
      ></div>
    </div>

    <ul class="hidden lg:flex gap-6 items-center">
      <li
        class="uppercase list-none text-sm"
        v-for="(link, index) in links"
        :key="index"
      >
        {{ link }}
      </li>
    </ul>
  </div>
</template>
