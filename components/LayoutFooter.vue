<script setup lang="ts">
import { defineProps, computed } from 'vue'
import { useNow } from '@vueuse/core'

const props = defineProps({
  eventLogo: {
    type: String,
    default: ""
  },
  eventUrl: {
    type: String,
    default: ""
  },
  twitter: {
    type: String,
    default: ""
  },
  twitterUrl: {
    type: String,
    default: ""
  },
})

const now = useNow()

const date = computed(() => now?.value.toLocaleDateString('en-US'))

</script>
<template>
  <footer
    v-if="eventLogo || twitter"
    class="mt-auto flex items-center w-full text-primary dark:text-white z-10 justify-between"
  >
    <div class="mb-0 flex items-center">
      <template v-if="eventLogo">
        <a :href="eventUrl" target="_blank">
          <img :src="eventLogo" class="h-8 mr-4" alt="Event image" />
        </a>
        <span>&nbsp; - &nbsp;</span>
      </template>
      <span>{{ date }}</span>
    </div>
    <a v-if="twitter" :href="twitterUrl" target="_blank">{{ twitter }}</a>
  </footer>
</template>

<style scoped>
a {
  border-color: transparent;
}
</style>
