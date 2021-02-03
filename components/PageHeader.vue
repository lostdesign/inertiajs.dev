<template>
  <div
    class="py-12 px-4 sm:py-18 sm:px-6 lg:px-8 lg:flex lg:justify-between border-b border-gray-300 mb-4"
  >
    <div class="max-w-xl">
      <h2
        class="text-4xl font-extrabold text-gray-900 sm:text-5xl sm:tracking-tight lg:text-6xl"
      >
        InertiaJS DEV
      </h2>
      <p class="mt-5 text-xl text-gray-600">
        The platform to get started with inertia, learn in-depth knowledge
        and more.
      </p>
    </div>
    <div class="mt-10 w-full max-w-xs">
      <search-input />
    </div>
  </div>
</template>

<script>
import SearchInput from '@/components/searchComponent'
export default {
  components: { SearchInput }
}
</script>
