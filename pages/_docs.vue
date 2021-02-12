<template>
  <div class="flex h-full">
    <div class="p-4 w-1/5 h-full bg-gray-900">
      <nuxt-link class="text-xl text-white" to="/">Team Orion</nuxt-link>
    </div>
    <div class="p-12 bg-gray-800 w-full">
      <nuxt-content
        :document="page"
        class="prose dark:prose-dark w-full"
      ></nuxt-content>
    </div>
  </div>
</template>

<style lang="postcss" scoped>
>>> .icon.icon-link {
  @apply h-7 w-7 bg-cover inline-block text-white;
  background-image: url('~assets/icon-hashtag.svg');
}
</style>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData(ctx) {
    const page = await ctx.$content(ctx.params.docs).fetch()

    return {
      page,
    }
  },
})
</script>
