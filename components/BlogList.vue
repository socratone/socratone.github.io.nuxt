<template>
  <ul>
    <li class="blog-item" v-for="article of articles" :key="article.slug">
      <div class="blog-item__image-container">
        <picture>
          <!-- TODO: 레티나 디스플레이가 아닌 경우 1x 이미지를 불러올 수 있도록 설정 해야 한다. -->
          <source 
            type="image/webp" 
            :srcset="require(`~/assets/images/${article.img}@2x.webp`)" 
          />
          <source 
            type="image/png" 
            :srcset="require(`~/assets/images/${article.img}@2x.png`)" 
          />
          <img 
            :src="require(`~/assets/images/${article.img}@2x.png`)" 
            v-bind:alt="article.alt" 
            width="70" 
          />
        </picture>
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