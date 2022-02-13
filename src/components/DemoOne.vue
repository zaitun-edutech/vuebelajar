<template>
  <div>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
export default {
  name: "DemoOne",
  setup() {
    const name = ref("Awal");

    setTimeout(() => {
      name.value = "CodeVulution";
      console.log(name);
    }, 3000);
    return {
      name,
    };
  },
};
</script>

<style></style>
