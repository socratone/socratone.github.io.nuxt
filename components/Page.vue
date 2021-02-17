<template>
  <main class="main">
    <slot></slot>
  </main>
</template>

<style>
.main {
  flex-grow: 1;
}

.main *:first-child {
  margin-top: 0;
}
</style>
