<template>
  <article class="page">
    <slot></slot>
  </article>
</template>

<style>
.page {
  width: 0;
  flex-grow: 1;
  margin-right: 2rem;
}

.page:last-child {
  margin-right: 0;
}

.page h1:first-child {
  margin-top: 0;
}

@media screen and (max-width: 800px) {
  .page {
    margin-right: 0;
  }
}
</style>
