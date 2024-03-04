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
  {
    name: "Checkbox",
    href: "/checkbox",
  },
  {
    name: "RadioButton",
    href: "/radiobutton",
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
  left: 0;
  top: 62px;
  height: 100%;
  background: #fff;
  position: fixed;
  width: 250px;
  padding: 20px;
  transition: 0.2s;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.07);
  transform: translateX(-250px);
}
.sidebar.is-open {
  transform: translateX(0px);
}
.sidebar__link {
  display: block;
  border-radius: 12px;
  border: 2px solid #fff;
  transition: 0.2s;
  font-weight: bold;
  margin-bottom: 10px;
  &:hover {
    color: var(--primary);
  }
}
</style>