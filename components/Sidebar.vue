<template>
  <nav class="mb-5 pr-12">
    <ul>
      <li v-for="link of links" :key="link.id">
        <NuxtLink
          :to="`#${link.id}`"
          class="block truncate"
          :class="{
            'mb-2': link.depth === 2,
            'ml-3 pb-2': link.depth === 3
          }"
        >
          {{ link.text }}
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    links: {
      type: Array,
      default: () => { return [] }
    }
  }
}
</script>
