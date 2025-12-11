<script setup>
import "primeicons/primeicons.css";

const membershipInfo = [
  {
    title: "Join for Free",
    description:
      "Reach your fitness goals or maintain your healthy lifestyle with professional training and support from a positive and active online community.",
    bulletins: [
      "~600 Full-Length Workout Videos",
      "Customizable Calendar",
      "Healthy Recipes",
      "Health and Fitness Articles",
      "Positive and Supportive Online Community",
      "No Credit Card Needed",
    ],
  },
  {
    title: "WO Plus",
    description:
      "WO Plus includes everything you get with a free membership and adds brand new convenience features, fitness tools, and unique content.",
    bulletins: [
      "Ads-Free Website and Videos",
      "Surprise Me Workout Selection Tool",
      "Statistics for Your Activities",
      "Enter and Track Custom Workouts",
      "FB Plus Exclusive Workouts",
      "Trackers to See Your Progress",
      "FB Plus Content and Challenges",
      "Video Tags",
      "FB Plus Routines",
      "Rest Day Complete",
    ],
  },
];
</script>

<template>
  <div class="p-8 md:px-15 lg:px-40 mt-15">
    <h2 class="text-2xl md:text-4xl lg:text-5xl">Membership</h2>
    <div class="w-full border-b opacity-65 mt-4"></div>

    <div class="flex flex-col lg:flex-row gap-10 mt-10">
      <div
        v-for="(data, index) in membershipInfo"
        :key="index"
        class="bg-dark-slate-blue rounded-md p-10 md:px-20 flex flex-col gap-4 lg:grow"
      >
        <h3 class="text-3xl lg:text-4xl">{{ data.title }}</h3>
        <p class="lg:max-w-100">{{ data.description }}</p>

        <ul class="flex flex-col gap-2 px-4 lg:text-sm mb-10 lg:mt-5">
          <li v-for="(bulletin, index) in data.bulletins" :key="index">
            {{ bulletin }}
          </li>
        </ul>

        <div
          class="md:text-lg lg:text-sm flex items-center gap-2 mt-auto"
          :class="
            index === 0
              ? 'text-orange'
              : 'bg-orange p-2.5 rounded-xl self-start'
          "
        >
          {{ index === 0 ? "See More" : "Join Club Now!" }}
          <span
            class="text-off-white"
            :class="index === 0 && 'pi pi-arrow-right'"
          />
        </div>
      </div>
    </div>
  </div>
</template>
