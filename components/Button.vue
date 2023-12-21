<script setup lang="ts">
const props = withDefaults(defineProps<{
  intent?: 'primary' | 'secondary'
  size?: 'normal' | 'large'
}>(), {
  intent: 'primary',
  size: 'large',
})

const buttonClass = computed(() => {
  return cva(
    'relative rounded-8 transition-300 ease-in-out '
    + 'hover:(-translate-4px shadow-[4px_4px_0])',
    {
      variants: {
        intent: {
          primary: 'bg-yellow text-black hover:(shadow-amber-6)',
          secondary: 'bg-blue-9 text-white hover:(shadow-blue)',
        },
        size: {
          normal: 'px-6 py-3 text-sm font-extrabold',
          large: 'px-8 py-4 text-lg font-extrabold',
        },
      },
    },
  )({
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
