<template>
  <a-layout-content
    :style="{
      margin: '24px 16px',
      padding: '24px',
      background: '#fff',
      minHeight: '280px',
    }"
  >
  <a-row type="flex" justify="space-around" align="middle">
      <a-col :span="6" align="center">
          <router-view></router-view>
      </a-col>
  </a-row>
  </a-layout-content>

</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  setup() {
    return {};
  },
});
</script>
<style scoped>
  
</style>