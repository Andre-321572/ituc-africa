<script setup>
useHead({
  title: 'CSI-Afrique | ITUC-Africa',
  meta: [
    { name: 'description', content: "Organisation Régionale Africaine de la Confédération Syndicale Internationale (CSI). Créer un monde meilleur pour les travailleurs en Afrique et au-delà." },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: 'https://ituc-africa.org/IMG/logo/siteon0.jpg' }
  ],
  htmlAttrs: {
    lang: 'fr'
  }
})

useSeoMeta({
  title: 'CSI-Afrique | ITUC-Africa',
  ogTitle: 'CSI-Afrique | ITUC-Africa',
  description: 'Créer un monde meilleur pour les travailleurs en Afrique et au-delà.',
  ogDescription: 'Représenter les travailleurs en Afrique à travers l\'unité, le plaidoyer et le renforcement des capacités.',
  ogImage: 'https://ituc-africa.org/IMG/logo/siteon0.jpg',
  twitterCard: 'summary_large_image',
})
</script>

<template>
  <div class="app-wrapper">
    <NuxtPage />
  </div>
</template>

<style>
/* Base transitions for page changes if needed */
.page-enter-active,
.page-leave-active {
  transition: opacity 0.5s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
}
</style>
