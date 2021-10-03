<template>
  <section>
    <PostList :posts="postList" />
  </section>
</template>

<script>
export default {
  async asyncData (context) {
    const postList = await context
      .$content('artigos')
      .fetch()

    return {
      postList
    }
  }
}
</script>
