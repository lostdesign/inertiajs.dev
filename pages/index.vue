<template>
  <div class="container px-8">
    <template v-for="c in content">
      <div :key="c.title">
        <NuxtLink :to="c.dir">
          {{ c.dir }}
        </NuxtLink>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  async fetch () {
    this.content = await this.$content({deep: true})
      .only('dir')
      .fetch()
  },
  data () {
    return {
      content: []
    }
  }
}
</script>
