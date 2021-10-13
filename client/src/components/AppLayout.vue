<template>
  <div class="layout">
    <header><slot name="header"></slot></header>
    <main><slot></slot></main>
    <footer><slot name="footer"></slot></footer>
  </div>
</template>

<script>
export default {
};
</script>

<style scoped>
header,
footer {
  height: 100px;
  background-color: green;
}
</style>
