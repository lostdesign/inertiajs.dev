<template>
  <div>
    <PageHeader />
    <BreadCrumb :path="$nuxt.$route.path" />
    <Nuxt />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader'

export default {
  components: {
    PageHeader
  }
}
</script>
