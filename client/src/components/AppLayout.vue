<template>
  <div class="layout">
    <header><slot name="header"></slot></header>
    <main><slot></slot></main>
    <footer><slot name="footer"></slot></footer>
  </div>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
header {
  height: 200px;
  background-color: green;
  color: white;
}
footer {
  height: 200px;
  background-color: green;
  color: white;
}
</style>
