<template>
  <aside class="category" v-bind:class="{ 'category--mobile': isMobile }">
    <nav>
      <ul>
        <li class="category__link-container">
          <router-link class="category__link" to="/category">
            전체보기
          </router-link>
        </li>
        <li class="category__link-container">
          <router-link class="category__link" to="/category/algorithm">
            Algorithm
          </router-link>
        </li>
        <li class="category__link-container">
          <router-link class="category__link" to="/category/typescript">
            TypeScript
          </router-link>
        </li>
        <li class="category__link-container">
          <router-link class="category__link" to="/category/docker">
            Docker
          </router-link>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script>
export default {
  props: ['isMobile']
}
</script>

<style scoped>
.category {
  width: 18rem;
  flex-shrink: 0;
}

.category__link-container {
  text-align: right;
  margin-bottom: 0.5rem;
}

.category__link {
  color: var(--color-font-secondary);
}

@media screen and (max-width: 800px) {
  .category {
    display: none;
  }

  .category--mobile {
    display: block;
    width: 100%;
  }
}
</style>
