<script setup lang="ts">
import { ref, provide } from 'vue'

const url = useRequestURL()
const route = useRoute()

const PROD_DOMAINS = ['keevia.id', 'www.keevia.id']

const isProdDomain
  = import.meta.env.PROD
    && PROD_DOMAINS.includes(url.hostname)

useHead(() => {
  if (!isProdDomain) {
    return {
      link: [
        {
          rel: 'icon',
          type: 'image/x-icon',
          href: '/favicon.ico'
        },
        {
          rel: 'icon',
          type: 'image/png',
          sizes: '32x32',
          href: '/favicon.png'
        },
        {
          rel: 'icon',
          type: 'image/png',
          sizes: '16x16',
          href: '/favicon.png'
        }
      ]
    }
  }

  // production domain → inject canonical dynamic
  return {
    link: [
      {
        rel: 'canonical',
        href: `https://keevia.id${route.fullPath}`
      },
      {
        rel: 'icon',
        type: 'image/x-icon',
        href: '/favicon.ico'
      },
      {
        rel: 'icon',
        type: 'image/png',
        sizes: '32x32',
        href: '/favicon.png'
      },
      {
        rel: 'icon',
        type: 'image/png',
        sizes: '16x16',
        href: '/favicon.png'
      }
    ]
  }
})

const isPlaying = ref(false)

const toggleAudio = () => {
  isPlaying.value = !isPlaying.value
}

provide('audioControl', {
  isPlaying,
  toggleAudio
})
</script>

<template>
  <div>
    <!-- <Navbar /> -->

    <main>
      <NuxtPage />
      <!-- Global Audio Player, hidden -->
      <iframe
        v-if="isPlaying"
        width="0"
        height="0"
        src="https://www.youtube.com/embed/Aa29L3jtg-o?autoplay=1&loop=1&playlist=Aa29L3jtg-o"
        allow="autoplay"
      ></iframe>
      <FloatingButtons />
    </main>
  </div>
</template>
