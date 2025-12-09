<script setup>
import { motion } from "motion-v";
import { ref } from "vue";

const links = [
  "Workouts",
  "Programs",
  "Healthy Living",
  "Community",
  "About",
  "Store",
];

const props = defineProps({
  close: Function,
});

const isClosing = ref(false);

const handleClose = () => {
  isClosing.value = true;

  setTimeout(() => {
    props.close();
  }, 1000);
};
</script>

<template>
  <motion.div
    :initial="{ translateY: -350 }"
    :animate="
      isClosing
        ? { translateY: -350, transition: { duration: 0.5 } }
        : { translateY: 0, transition: { duration: 0.5 } }
    "
    class="fixed top-20 left-[50%] -translate-x-[50%] h-auto w-3/4 bg-off-white/95 text-black p-5 rounded-md shadow-sm"
  >
    <span @click="handleClose" class="text-sm absolute right-6 top-3"
      >close</span
    >

    <ul class="flex flex-col gap-4 mt-10 items-center">
      <li
        class="uppercase font-semibold"
        v-for="(link, index) in links"
        :key="index"
      >
        {{ link }}
      </li>
    </ul>
  </motion.div>
</template>
