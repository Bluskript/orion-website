<template>
  <div class="flex h-full">
    <div class="p-4 w-1/5 h-full bg-gray-900">
      <nuxt-link class="text-xl text-white" to="/">Team Orion</nuxt-link>
    </div>
    <div class="p-12 bg-gray-800 w-full overflow-auto">
      <nuxt-content
        :document="page"
        class="prose dark:prose-dark w-full"
      ></nuxt-content>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component } from 'nuxt-property-decorator'
import { IContentDocument } from '@nuxt/content/types/content'

@Component({
  async asyncData(ctx) {
    const page = await ctx.$content(ctx.params.id || '404').fetch()
    const articles = await ctx.$content().only('title').fetch()

    console.log(articles)

    return { page }
  },
  head(this: Docs) {
    return {
      title: this.page?.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.page?.description,
        },
        // Open Graph
        { hid: 'og:title', property: 'og:title', content: this.page?.title },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.page?.description,
        },
        // Twitter Card
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.page?.title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.page?.description,
        },
      ],
    }
  },
})
export default class Docs extends Vue {
  page?: IContentDocument = undefined
}
</script>

<style lang="postcss" scoped>
>>> .icon.icon-link {
  @apply h-7 w-7 bg-cover inline-block text-white;
  background-image: url('~assets/icon-hashtag.svg');
}
</style>
