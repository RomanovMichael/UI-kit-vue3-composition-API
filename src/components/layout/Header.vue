<script setup>
</script>

<template>
  <header class="header">
    <router-link class="header__link" to="/"
      >UI Kit (Vue 3 + Composition API)</router-link
    >
  </header>
</template>



<style lang='scss' scoped>
.header {
  position: relative;
  background: #fff;
  font-weight: bold;
  padding: 0 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.07);
  height: 62px;
  display: flex;
  align-items: center;
  z-index: 1;
}
.header__link {
  &:hover {
    color: var(--primary);
  }
}
</style>