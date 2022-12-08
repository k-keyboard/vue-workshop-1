<template>
  <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible>
    <div class="logo" />
    <div align="center" style="padding: 20px 0 10px 0">
      <a-button
        @click="toggleCollapse"
        type="primary"
        shape="circle"
        size="large"
      >
        K
      </a-button>
    </div>

    <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
      <a-menu-item key="1">
        <user-outlined />
        <span>
          <router-link id="white" to="/">Home</router-link>
        </span>
      </a-menu-item>
      <a-menu-item key="2">
        <video-camera-outlined />
        <span>
          <router-link id="white" to="/about">About</router-link>
        </span>
      </a-menu-item>
      <a-menu-item key="3">
        <code-outlined />
        <span>
          <router-link id="white" to="/workshop-1">Workshop-1</router-link>
        </span>
      </a-menu-item>
    </a-menu>
  </a-layout-sider>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import {
  UserOutlined,
  VideoCameraOutlined,
  CodeOutlined,
} from "@ant-design/icons-vue";

export default defineComponent({
  props: ["collapsed"],
  components: {
    UserOutlined,
    VideoCameraOutlined,
    CodeOutlined,
  },
  setup(props, { emit }) {
    const selectedKeys = ref(0);
    const toggleCollapse = () => {
      emit("update:collapsed", !props.collapsed);
    };
    return {
      toggleCollapse,
      selectedKeys,
    };
  },
});
</script>

<style scoped>
#white {
  color: white;
}
</style>
