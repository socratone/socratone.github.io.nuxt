<template>
  <header class="header">
    <nav class="header__nav">
      <p class="header__title">
        <router-link to="/">SOCRATONE</router-link>
      </p>
      <ul class="header__list">
        <li class="header__list-item">
          <router-link to="/category">개발</router-link>
        </li>
        <li class="header__list-item">
          <router-link to="/category">음악</router-link>
        </li>
      </ul>
      <button class="header__bars-button">
        <svg width="20" height="20" class="hidden" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 341.333 341.333">
          <path d="M0 277.333h341.333V320H0zm0-128h341.333V192H0zm0-128h341.333V64H0z"></path>
        </svg>
      </button>
    </nav>
  </header>
</template>

<style>
.header {
  height: 5rem;
  border-bottom: 1px solid var(--color-border);
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

.header__bars-button {
  

  display: none;
}

@media screen and (max-width: 800px) {
  .header__list {
    display: none;
  }

  .header__bars-button {
    display: flex;
    align-items: center;
  }
}
</style>
