<script lang="ts" setup>
import BaliAesthetic from '~/components/bali-aesthetic.vue';

const formattedName = 'Darma & Dewi'
const slug = 'darma-dewi'
const domain = 'https://undangandigital.keevia.id'

useHead({
  meta: [
    { name: 'google-site-verification', content: 'GSC_VERIFICATION_TAG_FOR_DARMA_DEWI' }
  ]
})

useSeoMeta({
  title: `Pawiwahan ${formattedName} | Keevia.id`,
  description: `Join us in celebrating the pawiwahan of ${formattedName}. With love and joy, we invite you to be part of our special day.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `Undangan Pawiwahan ${formattedName}`,
  ogDescription: `With love and happiness, ${formattedName} invite you to celebrate their pawiwahan day.`,
  ogType: 'website',
  ogUrl: `${domain}/${slug}`,
  ogImageType: 'image/jpeg',
  ogSiteName: 'Keevia.id',
  ogLocale: 'id_ID',

  // Twitter
  twitterCard: 'summary_large_image',
  twitterTitle: `Undangan Pawiwahan ${formattedName}`,
  twitterDescription: `Join us in celebrating the pawiwahan of ${formattedName}.`
})
</script>

<template>
  <div>
    <BaliAesthetic 
    />
  </div>
</template>
