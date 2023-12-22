<script setup lang="ts">
import type { PresentBoxState } from '~/types'

defineProps<{
  state: PresentBoxState
}>()

const emit = defineEmits<{
  click: [event: any]
}>()
</script>

<template>
  <div isolate relative aspect-square max-w-90 w-full h-full p-5>
    <div absolute inset-0 z--1 rounded="50%" bg-amber blur-3xl />

    <template v-if="state === 'floating'">
      <NuxtImg
        src="/present.png" alt="Подарък"
        class="animate-up-down cursor-pointer"
        preload loading="lazy"
        @click="emit('click', $event)"
      />
    </template>

    <div v-else class="animate-shake">
      <NuxtImg preload translate-y-14px src="/present-head.png" alt="Капак на подарък" loading="lazy" />
      <NuxtImg preload translate-y--13px src="/present-body.png" alt="Тяло на подарък" loading="lazy" />
    </div>
  </div>
</template>

<style>
@keyframes up-down {
  from {
    transform: translate3d(0, 10px, 0);
  }

  to {
    transform: translate3d(0, -10px, 0);
  }
}

@keyframes down {
  to {
    transform: translate3d(0, 10px, 0);
  }
}

@keyframes shake {
  25% {
    transform: rotate3d(0, 0, 1, 6deg);
  }
  75% {
    transform: rotate3d(0, 0, 1, -6deg);
  }
}

.animate-up-down {
  animation: down 1.5s ease-in-out both;
  animation: up-down 6s ease-in-out 1.5s infinite alternate;
}

.animate-shake {
  animation: shake 500ms ease-out 1s;
}
</style>
