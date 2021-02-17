<template>
  <div>
    <Header />
    <Body>
      <Page>
        <!-- TODO: 동적으로 수정 -->
        <h1>TypeScript</h1>
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <img :src="require(`~/assets/images/${article.img}`)" width="100" />
              <div>
                <h2>{{ article.title }}</h2>
                <p>by {{ article.author }}</p>
                <p>{{ article.description }}</p>
              </div>
            </NuxtLink>
          </li>
        </ul>
      </Page>
      <Category />
    </Body>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // TODO: 삭제하거나 수정
      title: 'TypeScript'
    }
  },
  async asyncData({ $content, params, query }) {
    const articles = await $content('articles', params.slug)
      .where({
        'category': {
          $regex: [query.category, 'i']
        }
      })
      // .without('body')
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles
    }
  }
}
</script>

<style>

</style>
