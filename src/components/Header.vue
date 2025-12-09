<script setup>
const menubars = [1, 2, 3];

defineProps({
  open: Function,
});
</script>

<template>
  <div
    id="nav"
    class="h-10 w-full py-6 px-5 flex justify-between items-center bg-black relative z-20"
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

    <ul class="hidden">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>
