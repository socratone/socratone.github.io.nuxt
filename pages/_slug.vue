<template>
  <div>
    <Header />
    <Body>
      <Page>
        <nuxt-content :document="article" />
      </Page>
      <Category />
    </Body>
  </div>
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
  .nuxt-content p {
    margin-bottom: 2rem;
  }

  .nuxt-content pre {
    border-radius: 12px;
    margin-bottom: 2rem;
    font-size: 1.6rem;
  }
</style>