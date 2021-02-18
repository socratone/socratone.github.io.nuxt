<template>
  <header class="header">
    <nav class="header__nav">
      <p class="header__title">
        <router-link to="/">SOCRATONE</router-link>
      </p>
      <ul class="header__list">
        <li class="header__list-item">
          <router-link to="/category">BLOG</router-link>
        </li>
      </ul>
      <button class="header__bars-button" v-on:click="handleBarsClick">
        <svg width="20" height="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 341.333 341.333">
          <path d="M0 277.333h341.333V320H0zm0-128h341.333V192H0zm0-128h341.333V64H0z"></path>
        </svg>
      </button>
      <section class="header__category-container" v-if="isClickBars">
        <div class="header__x-container">
          <button class="header__bars-button" v-on:click="handleBarsClick">
            <svg width="20" height="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 386.667 386.667">
              <path d="m386.667 45.564-45.564-45.564-147.77 147.769-147.769-147.769-45.564 45.564 147.769 147.769-147.769 147.77 45.564 45.564 147.769-147.769 147.769 147.769 45.564-45.564-147.768-147.77z"/>
            </svg>
          </button>
        </div>
        <Category v-bind:isMobile="true" />
      </section>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isClickBars: false
    }
  },
  methods: {
    handleBarsClick: function () {
      if (this.isClickBars === false) this.isClickBars = true;
      else this.isClickBars = false;
    }
  }
}
</script>

<style scoped>
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

.header__x-container {
  height: 5rem;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.header__category-container {
  position: fixed;
  z-index: 1;
  top: 0;
  right: 0;
  width: 18rem;
  height: 100vh;
  padding-right: 2rem;
  background: white;
  border-left: 1px solid var(--color-border);
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
