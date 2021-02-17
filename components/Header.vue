<template>
  <header class="header">
    <nav class="header__nav">
      <p class="header__title">
        <router-link to="/">SOCRATONE</router-link>
      </p>
      <ul class="header__list">
        <li class="header__list-item">
          <router-link to="/blog">개발</router-link>
        </li>
        <li class="header__list-item">
          <router-link to="/blog">음악</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style>
.header {
  height: 5rem;
  border-bottom: 1px solid gainsboro;
}

.header__nav {
  max-width: 1024px;
  height: 100%;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header__title {
  margin: 0;
}

.header__list {
  display: flex;
}

.header__list-item {
  margin-right: 2rem;
}

.header__list-item:last-child {
  margin-right: 0;
}
</style>
