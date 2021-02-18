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
      .where({
        author: 'socratone' // 없어야 하지만 where 메소드를 빼면 에러가 발생한다.
      })
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