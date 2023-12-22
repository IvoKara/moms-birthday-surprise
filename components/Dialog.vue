<template>
  <div
    role="dialog"
    fixed z-10 inset-6 rounded-4 p-10
    bg="#D79C42" overflow-auto
  >
    <div>
      <ContentQuery v-slot="{ data }" path="/wish" find="one">
        <ContentRenderer class="text-start prose" :value="data" />
      </ContentQuery>
    </div>
  </div>
</template>
