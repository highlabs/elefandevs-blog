<template>
  <section>
    <h1>Posts</h1>
    <div>
      <ul>
        <li v-for="post in posts" :key="post.slug">
          <h2>{{ post.title }}</h2>
          <p>{{ post.description }}</p>
          <nuxt-link :to="post.path">Ler artigo</nuxt-link>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      default: () => []
    }
  }
}
</script>
