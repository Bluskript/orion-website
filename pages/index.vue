<template>
  <div>
    <banner class="bg-gray-900 p-16">
      <h1 class="text-8xl font-bold text-blue-300 mt-32">Team Orion</h1>
      <div class="ml-3">
        <p class="text-lg mt-6 font-thin text-blue-200">
          A team from the USA with some epic hardware and software
        </p>
        <h-button
          class="mt-6 view-docs-btn"
          @click.native="$router.push('/docs')"
        >
          View Docs
          <h-icon icon="mdiChevronRight" class="icon" />
        </h-button>
      </div>
    </banner>
    <div class="text-center items-center flex flex-col bg-gray-800 -mt-12 p-8">
      <h1 class="text-6xl mt-16 text-white">Features</h1>
      <div class="shadow-xl w-1/5 p-4 mt-10 bg-gray-700">
        <p>- nothing</p>
        <p>- nothing</p>
        <p>- nothing</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Banner from '~/components/HBanner.vue'
import HButton from '~/components/HButton.vue'

export default Vue.extend({
  components: { Banner, HButton },
})
</script>

<style lang="postcss" scoped>
.view-docs-btn {
  & > .icon {
    @apply ml-1 transform;
    transition: opacity, transform 200ms;
  }

  &:hover {
    & > .icon {
      @apply translate-x-1 opacity-100;
    }
  }
}
</style>
