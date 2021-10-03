<template>
  <article>
    <h1>{{ post.title }}</h1>
    <h2>{{ post.description }}</h2>
    <ul v-if="post.categories">
      <li v-for="category in post.categories" :key="category">
        {{ category }}
      </li>
    </ul>
    <nuxt-content :document="post" />
  </article>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const post = await $content('artigos')
      .where({ slug: params.slug })
      .fetch()

    return {
      post: post[0]
    }
  }
}
</script>

<style lang="postcss" scoped>
  article {
    @apply prose;
  }
</style>
