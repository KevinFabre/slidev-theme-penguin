<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps({
  logoHeader: {
    type: String,
  },
  eventLogo: {
    type: String,
  },
  eventUrl: {
    type: String,
  },
  twitter: {
    type: String,
  },
  twitterUrl: {
    type: String,
  },
})
</script>

<template>
  <div class="bg-main slidev-layout intro">
    <LayoutHeader :logo-header="logoHeader" />
    <CornerCurves class="absolute left-0 top-0 transform rotate-90" />
    <div class="flex flex-col justify-center text-center">
      <slot />
    </div>
    <LayoutFooter
      :event-logo="eventLogo"
      :event-url="eventUrl"
      :twitter="twitter"
      :twitter-url="twitterUrl"
    />
    <Zigzags class="absolute top-20 -right-30" />
  </div>
</template>

<style>
.slidev-layout.intro {
  h1 {
    @apply text-6xl leading-20 font-title font-extrabold;
  }

  h1 + p {
    @apply opacity-60 -mt-4 text-2xl;
  }

  a {
    @apply text-secondary-400 hover:text-secondary-500 dark:(text-white hover:text-gray-200);
  }
}
</style>
