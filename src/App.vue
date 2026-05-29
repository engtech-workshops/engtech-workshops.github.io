<script setup lang="ts">
import { workshops } from "@/workshoplist"
import WorkshopCard from "@/components/WorkshopCard.vue"
</script>

<template>
  <div class="w-full max-w-6xl p-4 flex flex-col mx-auto gap-3">
    <div class="p-2 flex flex-col justify-end rounded text-2xl font-bold h-20 bg-primary text-primary-foreground head-banner">
      Engineering and Technology Workshops
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 flex-wrap gap-4">
      <WorkshopCard v-for="workshop in workshops" :key="workshop.title" :workshop="workshop" class="flex-1"/>
    </div>
  </div>
</template>

<style scoped>
.head-banner {
  background: linear-gradient(60deg, oklch(54.2% 0.034 322.5), oklch(71.1% 0.019 323.02), oklch(70.4% 0.04 256.788), oklch(50% 0.134 242.749));
}
</style>
