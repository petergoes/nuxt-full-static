<template>
  <main>
    <h1>{{ doc.title }}</h1>
    <nuxt-content :document="doc" />
  </main>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const doc = await $content(params.slug).fetch()
    return { doc }
  }
}
</script>
