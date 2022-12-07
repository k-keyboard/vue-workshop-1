<template>
  <a-layout style="min-height: 100vh">
    <!-- Menu -->
    <!-- <span>{{ collapsed }}</span> -->
    <Menu v-model:collapsed="collapsed" />
    <a-layout>
      <!-- Header -->
      <Header v-model:collapsed="collapsed"/>
      <!-- Content -->
      <Content />
    </a-layout>
  </a-layout>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
import Content from "./components/core/Content.vue";
import Header from "./components/core/Header.vue";
import Menu from "./components/core/Menu.vue";
export default defineComponent({
  components: {
    Menu,
    Header,
    Content,
  },
  setup() {
    return {
      selectedKeys: ref<string[]>(["1"]),
      collapsed: ref<boolean>(false),
    };
  },
});
</script>

