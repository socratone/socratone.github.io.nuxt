<!-- 블로그 글 -->
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
    head() {
      return {
        title: this.article.title,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.article.description
          },
          { 
            hid: 'keywords', 
            name: 'keywords', 
            content: this.article.category
          }
        ],
      }
    },
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()
      return { article }
    }
  }
</script>

<style>
  .nuxt-content pre {
    border-radius: 12px;
    margin-bottom: 2rem;
    font-size: 1.6rem;
  }

  .nuxt-content p {
    color: var(--color-font-secondary);
  }

  .nuxt-content a {
    color: dodgerblue;
  }

  .nuxt-content img {
    width: 100%;
  }
</style>