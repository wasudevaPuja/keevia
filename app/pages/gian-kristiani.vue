<script lang="ts" setup>
import Blossom from '~/components/blossom.vue';

const formattedName = 'Gian & Kristiani'
const slug = 'gian-kristiani'

useSeoMeta({
  title: `The Wedding of ${formattedName} | Keevia.id`,
  description: `Join us in celebrating the wedding of ${formattedName}. With love and joy, we invite you to be part of our special day.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `The Wedding of ${formattedName}`,
  ogDescription: `With love and happiness, ${formattedName} invite you to celebrate their wedding day.`,
  ogType: 'website',
  ogUrl: `https://undangandigital.keevia.id/${slug}`,
  ogImage: `https://res.cloudinary.com/debcjiypk/image/upload/f_jpg,c_fill,w_1200,h_630/v1773331570/cover_poiflp.jpg`,
  ogSiteName: 'Keevia.id',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogLocale: 'id_ID',

  // Twitter
  twitterCard: 'summary_large_image',
  twitterTitle: `The Wedding of ${formattedName}`,
  twitterDescription: `Join us in celebrating the wedding of ${formattedName}.`,
  twitterImage: `https://res.cloudinary.com/debcjiypk/image/upload/f_jpg,c_fill,w_1200,h_630/v1773331570/cover_poiflp.jpg`,
  twitterSite: '@keevia.id',
  twitterCreator: '@keevia.id'
})
</script>

<template>
  <div>
    <Blossom />
  </div>
</template>
