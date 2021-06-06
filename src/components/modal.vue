<template>
  <teleport to="#modal">
    <div class="hello">hello</div>
  </teleport>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "modal",
  props: {
    msg: String
  }
});
</script>

<style scoped lang="scss">
</style>
