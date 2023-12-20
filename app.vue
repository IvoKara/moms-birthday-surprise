<script setup lang="ts">
import { appName } from '~/constants'

useHead({
  title: appName,
})
</script>

<template>
  <!-- <VitePwaManifest /> -->
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<style>
html,
body,
#__nuxt {
  height: 100vh;
  margin: 0;
  padding: 0;
}

html {
  --uno: bg-[#2971f6] text-white font-sans;
}

h1,
h2,
h3 {
  --uno: font-serif;
}

html.dark {
  --uno: bg-blue-8;
}
</style>
