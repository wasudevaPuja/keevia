<script lang="ts" setup>
import BaliAesthetic from '~/components/bali-aesthetic.vue';

const formattedName = 'Darma & Dewi'
const slug = 'darma-dewi'
const domain = 'https://undangandigital.keevia.id'
const previewImg = 'https://res.cloudinary.com/debcjiypk/image/upload/v1773637621/Screenshot_2026-03-16_at_13.06.02_ylgkzt.png'

useHead({
  meta: [
    { name: 'google-site-verification', content: 'GSC_VERIFICATION_TAG_FOR_DARMA_DEWI' }
  ]
})

useSeoMeta({
  title: `Pawiwahan ${formattedName} | Keevia.id`,
  description: `Pawiwahan ${formattedName}. Dengan cinta dan bahagia, ${formattedName} mengundang Anda untuk menghadiri pawiwahan mereka.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `Undangan Pawiwahan ${formattedName}`,
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
  twitterTitle: `Undangan Pawiwahan ${formattedName}`,
  twitterDescription: `Dengan cinta dan bahagia, ${formattedName} mengundang Anda untuk menghadiri pawiwahan mereka.`,
  twitterImage: previewImg
})
</script>

<template>
  <div>
    <BaliAesthetic 
    />
  </div>
</template>
