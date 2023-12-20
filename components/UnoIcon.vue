<script setup lang="ts">
defineProps<{
  icon: `i-${string}`
}>()
</script>

<template>
  <i inline-block :class="icon" />
</template>
