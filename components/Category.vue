<template>
  <aside class="category">
    <nav>
      <ul>
        <li class="category__link-container">
          <router-link class="category__link" to="/category/typescript">
            TypeScript
          </router-link>
        </li>
        <li class="category__link-container">
          <router-link class="category__link" to="/category/javascript">
            JavaScript
          </router-link>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<style scoped>
.category {
  width: 18rem;
  flex-shrink: 0;
}

.category__link-container {
  margin-bottom: 0.5rem;
}

.category__link {
  color: var(--color-font-secondary);
}

@media screen and (max-width: 800px) {
  .category {
    display: none;
  }
}
</style>
