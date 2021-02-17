<template>
  <div>
    <Header />
    <Body>
      <Page>
        {{ title }}
      </Page>
      <Category />
    </Body>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'music'
    }
  },
}
</script>

<style>

</style>
