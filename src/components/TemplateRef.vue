<template>
  <div>
    <!-- <input type="text" placeholder="input focus" ref="inputRef" /> -->
    <br />
    <br />
    <input
      type="text"
      placeholder=" Composition input focus"
      ref="c_inputRef"
    />
  </div>
</template>

<script>
import { onMounted } from "@vue/runtime-core";
export default {
  name: "TempalateRef",
  setup() {
    const c_inputRef = ref(null);
    onMounted(() => {
      this.c_inputRef.value.focus();
    });
    return {
      c_inputRef,
    };
  },
  //   mounted() {
  //     this.$refs.inputRef.focus();
  //   },
};
</script>

<style>
</style>