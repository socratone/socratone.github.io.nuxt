<template>
  <div>
    <Header />
    <Body>
      <Page>
        <h1>{{ this.$route.params.slug }}</h1>
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
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

<style>

</style>
