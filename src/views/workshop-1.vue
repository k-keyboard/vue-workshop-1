<template>
  <a-col :span="10" align="center">
    <div :span="5">
      <h1 align="center">Workshop #1 - Limit Message</h1>
      <div class="input-group">
        <input
          type="text"
          class="input-limit"
          v-model="message"
          :maxlength="max"
        />
        <span class="text-limit" v-text="max - message.length"></span>
      </div>

      <p class="height-100">
        <a-input v-model:value="value1" show-count :maxlength="20" />
        <br />
        <br />
        <a-textarea v-model:value="value2" show-count :maxlength="100" />
      </p>
    </div>
  </a-col>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
export default defineComponent({
  data() {},
  setup() {
    const value1 = ref<string>();
    const value2 = ref<string>();
    const message = ref<string>("");
    const max = ref<string>("20");
    return {
      value1,
      value2,
      message,
      max: 20,
    };
  },
});
</script>
<style scoped>
.input-group {
  border: 1px solid #232323;
  margin: 20px 0;
  position: relative;
}
.input-limit {
  border: none;
  padding: 5px;
  width: 100%;
  padding-left: 0.5rem;
}
.text-limit {
  position: absolute;
  right: -15px;
  border-radius: 0 10px 10px 0;
  width: 20%;
  padding: 0.3rem;
}
</style>
