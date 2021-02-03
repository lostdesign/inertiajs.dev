<template>
  <div class="pb-4 mb-12 px-8 border-b border-gray-300">
    <nav class="hidden sm:flex" aria-label="Breadcrumb">
      <ol class="flex items-center space-x-4">
        <template v-for="breadcrumb in getBreadCrumbs()">
          <li :key="breadcrumb">
            <div class="flex items-center">
              <template v-if="breadcrumb !== 'Home' && breadcrumb !== ''">
                <svg class="flex-shrink-0 h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path fill-rule="evenodd" d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z" clip-rule="evenodd"/>
                </svg>
              </template>
              <NuxtLink :to="`/${breadcrumb === 'Home' ? '' : breadcrumb}`" class="text-sm font-medium text-gray-500 hover:text-gray-700 capitalize" :class="[breadcrumb === 'Home' ? '' : 'ml-4']">
                {{ breadcrumb }}
              </NuxtLink>
            </div>
          </li>
        </template>
      </ol>
    </nav>
  </div>
</template>

<script>
export default {
  props: {
    path: {
      type: String,
      default: 'Home'
    }
  },
  methods: {
    getBreadCrumbs () {
      return [
        'Home', ...this.path.split('/').slice(1)
      ]
    },
    getUrl (breadCrumb) {
      breadcrumb
      // if home => /
      // if any => return self
      // if last => return #
    }
  }
}
</script>
