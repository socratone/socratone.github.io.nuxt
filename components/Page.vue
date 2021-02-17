<template>
  <article class="page">
    <slot></slot>
  </article>
</template>

<style>
.page {
  flex-grow: 1;
  margin-right: 2rem;
}

.page h1:first-child {
  margin-top: 0;
}
</style>
