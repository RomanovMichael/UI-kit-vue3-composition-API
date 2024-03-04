<script setup>
import LayoutHeader from "@/components/layout/Header.vue";
import LayoutSidebar from "@/components/layout/Sidebar.vue";

import { ref } from "vue";

const isOpenSideBar = ref(false);
const toggleSidebar = () => {
  isOpenSideBar.value = !isOpenSideBar.value;
};
</script>

<template>
  <div class="container">
    <div @click="toggleSidebar" class="sidebar-toggle">></div>
    <layout-header />
    <layout-sidebar :openSidebar="isOpenSideBar" />
    <div :class="['content', { full: !isOpenSideBar }]">
      <router-view />
    </div>
  </div>
</template>

<style lang='scss'>
@import "@/styles/global.scss";

#app {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-synthesis: none;
}

.content {
  max-width: 1400px;
  margin-left: 250px;
  padding: 30px;
  transition: 0.2s;
}

.sidebar-toggle {
  position: fixed;
  top: 62px;
  left: 0;
  width: 15px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--primary);
  color: #fff;
  cursor: pointer;
  z-index: 1;
}

.content.full {
  margin-left: 0;
}

@media screen and (max-width: 1023px) {
  .content {
    margin-left: 0;
  }
}
</style>

