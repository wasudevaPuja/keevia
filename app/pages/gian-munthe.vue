<script lang="ts" setup>
import Blossom from '~/components/blossom.vue';

const formattedName = 'Gian & Kristiany'
const slug = 'gian-munthe'

useSeoMeta({
  title: `The Wedding of ${formattedName} | Keevia`,
  description: `Join us in celebrating the wedding of ${formattedName}. With love and joy, we invite you to be part of our special day.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `The Wedding of ${formattedName}`,
  ogDescription: `With love and happiness, ${formattedName} invite you to celebrate their wedding day.`,
  ogType: 'website',
  ogUrl: `https://keevia.id/${slug}`,
  ogImage: `https://keevia.id/images/${slug}-cover.jpg`,
  ogSiteName: 'Keevia.id',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogLocale: 'en_US',

  // Twitter
  twitterCard: 'summary_large_image',
  twitterTitle: `The Wedding of ${formattedName}`,
  twitterDescription: `Join us in celebrating the wedding of ${formattedName}.`,
  twitterImage: `https://keevia.id/images/${slug}-cover.jpg`,
  twitterSite: '@keevia.id',
  twitterCreator: '@keevia.id'
})
</script>

<template>
  <div>
    <Blossom />
  </div>
</template>
