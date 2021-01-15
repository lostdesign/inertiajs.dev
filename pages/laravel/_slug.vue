<template>
  <main>
    <div class="flex px-8">
      <div class="w-1/5">
        <div class="text-gray-400 text-xs mts-5 mb-2 font-medium uppercase">Table of contents</div>
        <sidebar :links="article.toc" />
      </div>
      <article class="flex-none w-4/5">
        <header class="border-b border-gray-300 mb-6">
          <h1 class="text-5xl -mt-2 pb-3 font-black">{{ article.title }}</h1>
          <p class="text-gray-600 pb-6">{{ article.description }}</p>
        </header>
        <nuxt-content :document="article" />
      </article>
    </div>
  </main>
</template>

<script>
import Sidebar from '@/components/Sidebar'
import BreadCrumb from '@/components/BreadCrumb'

export default {
  components: { Sidebar, BreadCrumb },
  async asyncData ({ $content, params }) {
    const article = await $content('laravel/', params.slug).fetch()

    return { article }
  }
}
</script>

<style>
.nuxt-content h1,
.nuxt-content h2,
.nuxt-content h3,
.nuxt-content h4,
.nuxt-content h5,
.nuxt-content h6 {
  @apply pt-6 pb-2 font-bold;
}

.nuxt-content h1 {
  @apply text-4xl;
}

.nuxt-content h2 {
  @apply text-2xl;
}
</style>
