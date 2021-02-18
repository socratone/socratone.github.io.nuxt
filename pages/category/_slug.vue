<!-- 카테고리에 해당하는 블로그 리스트 -->
<template>
  <div>
    <Header />
    <Body>
      <Page>
        <h1 class="title">{{ this.$route.params.slug }}</h1>
        <BlogList v-bind:articles="articles" />
      </Page>
      <Category />
    </Body>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('articles')
      .where({
        'category': {
          $regex: [params.slug, 'i']
        }
      })
      .sortBy('createdAt', 'desc')
      .fetch()

    return {
      articles
    }
  }
}
</script>

<style scoped>
.title {
  text-transform: capitalize;
}
</style>
