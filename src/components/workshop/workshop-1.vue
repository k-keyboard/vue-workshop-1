<template>
  <div>
    <h1 align="center">
      Workshop #1 - Limit Message
    </h1>
  <a-row type="flex" justify="space-around" align="middle">
    <a-col :span="6">
      <p class="height-100">
        <a-input v-model:value="value1" show-count :maxlength="20" />
          <br />
          <br />
          <a-textarea v-model:value="value2" show-count :maxlength="100" />
      </p>
    </a-col>
  </a-row>
</div>
  
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const value1 = ref<string>();
    const value2 = ref<string>();
    return {
      value1,
      value2,
    };
  },
});
</script>
