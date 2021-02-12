<template>
  <Nuxt />
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  head: {
    bodyAttrs: {
      class: 'dark',
    },
  },
})
</script>

<style lang="postcss">
html,
body,
#__nuxt,
#__layout {
  @apply w-full h-full;
}

html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
</style>
