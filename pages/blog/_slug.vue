<template>
  <article>
    <Header />
    <Body>
      <Page>
        <nuxt-content :document="article" />
      </Page>
      <Category />
    </Body>
  </article>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()

      return { article }
    }
  }
</script>

<style>
  .nuxt-content h1 {
    font-weight: bold;
    font-size: 2.5rem;
    margin: 3rem 0 2rem 0;
  }

  .nuxt-content h2 {
    font-weight: bold;
    font-size: 2rem;
    margin: 3rem 0 2rem 0;
  }

  .nuxt-content h3 {
    font-weight: bold;
    font-size: 22px;
    margin: 3rem 0 2rem 0;
  }

  .nuxt-content p {
    margin-bottom: 2rem;
  }

  .nuxt-content pre {
    border-radius: 12px;
    margin-bottom: 20px;
    font-size: 1.6rem;
  }
</style>