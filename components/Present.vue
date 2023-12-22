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
        preload
        @click="emit('click', $event)"
      />
    </template>

    <div v-else class="animate-shake">
      <NuxtImg
        src="/present-head.png" alt="Капак на подарък"
        class="translate-y-14px animate-open-box"
        preload
      />
      <NuxtImg
        src="/present-body.png" alt="Тяло на подарък"
        translate-y--13px
        preload
      />
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

@keyframes open-box {
  to {
    transform: translate3d(0, -30px, 0);
  }
}

.animate-up-down {
  animation: down 1.5s ease-in-out both;
  animation: up-down 6s ease-in-out 1.5s infinite alternate;
}

.animate-shake {
  animation: shake 500ms ease-out 1.3s;
}

.animate-open-box {
  animation: open-box 300ms ease-in-out 3s forwards;
}
</style>
