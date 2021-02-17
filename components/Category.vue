<template>
  <aside class="category">
    <nav>
      <ul>
        <li><router-link to="/category/typescript">TypeScript</router-link></li>
        <li><router-link to="/category/javascript">JavaScript</router-link></li>
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
