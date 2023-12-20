<script setup lang="ts">
const props = withDefaults(defineProps<{
  intent?: 'primary' | 'secondary'
  size?: 'normal' | 'large'
}>(), {
  intent: 'primary',
  size: 'large',
})

const buttonClass = computed(() => {
  return cva('rounded-8', {
    variants: {
      intent: {
        primary: 'bg-yellow text-black',
        secondary: 'bg-blue-9 text-white',
      },
      size: {
        normal: 'px-6 py-3 text-sm font-extrabold',
        large: 'px-8 py-4 text-lg font-extrabold',
      },
    },
  })({
    intent: props.intent,
    size: props.size,
  })
})
</script>

<template>
  <button :class="buttonClass">
    <slot />
  </button>
</template>
