<script lang="ts" setup>
import Blossom from '~/components/blossom.vue';

const formattedName = 'Gian & Kristiani'
const slug = 'gian-kristiani'
const domain = 'https://undangandigital.keevia.id'
const previewImg = 'https://res.cloudinary.com/debcjiypk/image/upload/v1773331434/gallery_3_ejaubq.jpg'

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
  ogUrl: `${domain}/${slug}`,
  ogImage: previewImg,
  ogImageSecureUrl: previewImg,
  ogImageType: 'image/jpeg',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogSiteName: 'Keevia.id',
  ogLocale: 'id_ID',

  // Twitter
  twitterCard: 'summary_large_image',
  twitterTitle: `The Wedding of ${formattedName}`,
  twitterDescription: `Join us in celebrating the wedding of ${formattedName}.`,
  twitterImage: previewImg
})
</script>

<template>
  <div>
    <Blossom />
  </div>
</template>
