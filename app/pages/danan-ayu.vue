<script lang="ts" setup>
import Monocrom from '~/components/monocrom.vue';

const formattedName = 'Danan & Ayu'
const slug = 'danan-ayu'
const domain = 'https://undangandigital.keevia.id'
const previewImg = 'https://assets.keevia.id/wedding-danan/IMG_3802.jpg'

useSeoMeta({
  title: `Pawiwahan of ${formattedName} | Keevia.id`,
  description: `Pawiwahan ${formattedName}. Dengan cinta dan bahagia, ${formattedName} mengundang Anda untuk menghadiri pawiwahan mereka.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `Pawiwahan of ${formattedName}`,
  ogDescription: `Dengan cinta dan bahagia, ${formattedName} mengundang Anda untuk menghadiri pawiwahan mereka.`,
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
  twitterTitle: `Pawiwahan of ${formattedName}`,
  twitterDescription: `Dengan cinta dan bahagia, ${formattedName} mengundang Anda untuk menghadiri pawiwahan mereka.`,
  twitterImage: previewImg
})
</script>

<template>
  <div>
    <Monocrom />
  </div>
</template>
