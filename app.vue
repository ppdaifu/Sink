<script setup lang="ts">
import { onMounted } from 'vue'

const { title, description, image } = useAppConfig()
useSeoMeta({
  title: title + ' - ' + description,
  description,
  ogType: 'website',
  ogTitle: title,
  ogDescription: description,
  ogImage: image,
  twitterTitle: title,
  twitterDescription: description,
  twitterImage: image,
  twitterCard: 'summary_large_image',
})
useHead({
  htmlAttrs: {
    lang: 'en',
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/icon-192.png',
    },
  ],
})

onMounted(() => {
  // Baidu Analytics
  const _hmt = (window as any)._hmt = (window as any)._hmt || [];
  (function() {
    const hm = document.createElement("script");
    hm.src = "https://hm.baidu.com/hm.js?7af9cc781ae0b1d55a016f7ae0dde530";
    const s = document.getElementsByTagName("script")[0]; 
    s.parentNode?.insertBefore(hm, s);
  })();
})
</script>

<template>
  <NuxtLayout>
    <NuxtLoadingIndicator color="#000" />
    <NuxtPage />
    <Toaster />
  </NuxtLayout>
</template>
