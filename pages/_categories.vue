<template>
  <div>
    <h1>Categorias</h1>
    <PostList :posts="postList" />
  </div>

</template>

<script>
export default {
  async asyncData (context) {
    const postList = await context
      .$content('artigos')
      .where({
        categories: { $contains: context.params.categories }
      })
      .fetch()

    return {
      postList
    }
  }
}
</script>
