<template>
  <ul>
    <li class="blog-item" v-for="article of articles" :key="article.slug">
      <div class="blog-item__image-container">
        <img :src="require(`~/assets/images/${article.img}`)" width="70" />
      </div>
      <div class="blog-item__text-container">
        <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
          <h2 class="blog-item__title">{{ article.title }}</h2>
          <p class="blog-item__description">{{ article.description }}</p>
        </NuxtLink>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['articles']
}
</script>

<style scoped>
.blog-item {
  display: flex;
  margin-bottom: 20px;
}

.blog-item__image-container {
  margin-right: 20px;
}

.blog-item__text-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.blog-item__title {
  margin: 0;
}

.blog-item__description {
  color: var(--color-font-secondary);
  margin: 0;
}
</style>