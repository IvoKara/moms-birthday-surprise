<template>
  <div isolate relative aspect-square max-h-90 p-5>
    <div absolute inset-0 z--1 rounded="50%" bg-amber blur-3xl />

    <NuxtImg class="animate-up-down" preload src="/present.png" alt="Подарък" />
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

.animate-up-down {
  animation: down 1.5s ease-in-out both;
  animation: up-down 6s ease-in-out 1.5s infinite alternate;
}
</style>
