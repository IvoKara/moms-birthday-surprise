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

    <Button @click="state = 'unboxing'">
      Отвори ме!
    </Button>
  </div>
</template>
