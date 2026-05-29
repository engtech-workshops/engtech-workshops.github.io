<script setup lang="ts">
import { Card, CardHeader, CardTitle, CardDescription, CardFooter } from "@/components/ui/card"
import { Button } from "@/components/ui/button"
import { PhRocket } from "@phosphor-icons/vue";
import type { Workshop } from "@/types"

const props = defineProps<{
  workshop: Workshop
}>()
const launchWorkshop = (link: string) => {
  window.open(link, '_blank')
}
</script>

<template>
  <Card class="flex flex-col">
    <CardHeader class="flex-1">
      <div class="flex flex-row">
        <div v-for="_ in 10" class="flex-1 h-2" :style="{ backgroundColor: workshop.color ?? 'brown', opacity: Math.random()*0.5+0.5 }"></div>
      </div>
      <CardTitle class="font-bold flex-1">{{ workshop.title }}</CardTitle>
      <CardDescription class="line-clamp-2" :title="workshop.description">{{ workshop.description }}</CardDescription>
    </CardHeader>
    <CardFooter class="flex flex-row">
      <Button class="grow" @click="launchWorkshop(workshop.link)" variant="secondary">Launch <PhRocket /></Button>
    </CardFooter>
  </Card>
</template>
