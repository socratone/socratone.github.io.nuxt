<template>
  <li class="tools-item">
    <div class="tools-item__image-container">
      <picture>
        <!-- TODO: 레티나 디스플레이가 아닌 경우 1x 이미지를 불러올 수 있도록 설정 해야 한다. -->
        <source 
          type="image/webp" 
          :srcset="require(`~/assets/images/${img}@2x.webp`)" 
        />
        <source 
          type="image/png" 
          :srcset="require(`~/assets/images/${img}@2x.png`)" 
        />
        <img 
          :src="require(`~/assets/images/${img}@2x.png`)" 
          :alt="alt" 
          width="70" 
        />
      </picture>
    </div>
    <div class="tools-item__text-container">
      <a :href="url" target="_blank">
        <h2 class="tools-item__title">{{ title }}</h2>
        <p class="tools-item__description">{{ description }}</p>
      </a>
    </div>
  </li>
</template>

<script>
export default {
  props: ['img', 'alt', 'title', 'description', 'url']
}
</script>

<style scoped>
.tools-item {
  display: flex;
  margin-bottom: 20px;
}

.tools-item__image-container {
  margin-right: 20px;
}

.tools-item__text-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.tools-item__title {
  margin: 0;
}

.tools-item__description {
  color: var(--color-font-secondary);
  margin: 0;
}
</style>