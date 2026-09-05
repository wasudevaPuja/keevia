<script lang="ts" setup>
import GoldElegan from '~/components/gold-elegan.vue';

const formattedName = 'I Gusti A. Ayu Galuh Parwati & I Gusti Ayu Cahya Pratiwi & I Gusti Ngurah Agung Alit Arya Wibawa & I Gusti Agung Ngurah Bratha Prasetya'
const slug = 'i-gusti-a-ayu-galuh-parwati-i-gusti-ayu-cahya-pratiwi-i-gusti-ngurah-agung-alit-arya-wibawa-i-gusti-agung-ngurah-bratha-prasetya'
const domain = 'https://undangandigital.keevia.id'
const previewImg = 'https://assets.keevia.id/mepandes/logo_jeroan.png'

useSeoMeta({
  title: `Undangan Mepandes ${formattedName} | Keevia.id`,

  description: `Dengan penuh rasa syukur, kami mengundang Anda untuk hadir dan memberikan doa restu dalam rangka Upacara Mepandes ${formattedName}.`,

  // Basic Meta
  author: 'Keevia.id',
  robots: 'index, follow',

  // Open Graph
  ogTitle: `Undangan Upacara Mepandes ${formattedName}`,
  ogDescription: `Dengan penuh rasa syukur, kami mengundang Anda untuk hadir dan memberikan doa restu dalam rangka Upacara Mepandes ${formattedName}.`,
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
  twitterTitle: `Undangan Upacara Mepandes ${formattedName}`,
  twitterDescription: `Dengan penuh rasa syukur, kami mengundang Anda untuk hadir dan memberikan doa restu dalam rangka Upacara Mepandes ${formattedName}.`,
  twitterImage: previewImg
})
</script>

<template>
  <div>
    <GoldElegan />
  </div>
</template>
