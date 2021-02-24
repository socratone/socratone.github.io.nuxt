<!-- 홈 -->
<template>
  <div>
    <Header />
    <portfolio />
  </div>
</template>

<style scoped>
.tools-item-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

@media screen and (max-width: 1024px) {
  .tools-item-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (max-width: 680px) {
  .tools-item-container {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
