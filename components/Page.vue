<template>
  <main class="page">
    <slot></slot>
  </main>
</template>

<style>
.page {
  flex-grow: 1;
  margin-right: 2rem;
}

.page *:first-child {
  margin-top: 0;
}
</style>
