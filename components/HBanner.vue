<template>
  <div class="banner">
    <slot />
  </div>
</template>

<style lang="postcss" scoped>
.banner {
  @apply h-4/6;
  background: repeating-linear-gradient(
    45deg,
    theme('colors.gray.800'),
    theme('colors.gray.800') 3px,
    theme('colors.gray.900') 3px,
    theme('colors.gray.900') 30px
  );
  clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%);
}
</style>
