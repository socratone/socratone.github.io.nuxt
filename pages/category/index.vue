<!-- 전체 블로그 리스트 -->
<template>
  <div>
    <Header />
    <Body>
      <Page>
        <h1>전체보기</h1>
        <BlogList v-bind:articles="articles" />
      </Page>
      <Category />
    </Body>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const articles = await $content('articles')
      .sortBy('createdAt', 'desc')
      .fetch()

    return {
      articles
    }
  }
}
</script>

<style>
</style>