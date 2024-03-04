<script setup>
import { ref } from "vue";

const props = defineProps({
  openSidebar: {
    type: Boolean,
    required: true,
  },
});

const links = ref([
  {
    name: "Typography",
    href: "/typography",
  },
  {
    name: "Button",
    href: "/button",
  },
]);
</script>

<template>
  <aside :class="['sidebar', { 'is-open': openSidebar }]">
    <router-link
      v-for="link in links"
      :key="link.name"
      :to="link.href"
      class="sidebar__link"
      >{{ link.name }}
    </router-link>
  </aside>
</template>

<style lang="scss" scoped>
.sidebar {
  position: fixed;
  left: 0;
  top: 62px;
  width: 250px;
  height: 100%;
  padding: 20px;
  background: #fff;
  box-shadow: 0 0 10 rgba(0, 0, 0, 0.07);
  transform: translateX(-250px);
  transition: 0.2s;
}

.sidebar.is-open {
  transform: translateX(0);
}

.sidebar__link {
  display: block;
  border-radius: 12px;
  padding: 10px;
  margin-bottom: 10px;
  border: 2px solid #fff;
  font-weight: bold;
  transition: 0.2s;
  &:hover {
    border-color: var(--primary);
  }
}
</style>