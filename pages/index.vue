<template>
  <div>
    <Header />
    <Body>
      <main class="main">
        <Logo />
      </main>
    </Body>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Hello World!!!!'
    }
  },
}
</script>

<style scoped>
  .main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
