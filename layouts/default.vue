<template>
  <main h-inherit px-10 py-20 text-center flex="~ col" justify-between>
    <div />

    <div h-full grid="~ cols-1" items-center>
      <slot />
    </div>

    <Footer mt-10 z--1 />
  </main>
</template>
