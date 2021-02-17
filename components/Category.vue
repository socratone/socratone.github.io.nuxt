<template>
  <aside class="category">
    <nav>
      <ul>
        <li><router-link to="/blog?category=typescript">TypeScript</router-link></li>
      </ul>
    </nav>
  </aside>
</template>

<style>
.category {
  flex-grow: 0;
  flex-shrink: 0;
  width: 20rem;
}
</style>
