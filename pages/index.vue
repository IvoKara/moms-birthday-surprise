<script setup lang="ts">
import type { PresentBoxState } from '~/types'

const state = ref<PresentBoxState>('floating')
</script>

<template>
  <div flex="~ col" items-center gap-20>
    <Present
      v-bind="{ state }"
      @click="state = 'unboxing'"
    />

    <Button
      :class="{ 'animate-go-away': state === 'unboxing' }"
      @click="state = 'unboxing'"
    >
      Отвори ме!
    </Button>
  </div>
</template>

<style>
@keyframes go-away {
  to {
    scale: 0;
    opacity: 0;
    filter: blur(20px);
  }
}

.animate-go-away {
  animation: go-away 1s ease-in-out forwards;
}
</style>
