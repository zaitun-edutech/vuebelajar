<template>
  <h3>Option {{ o_firstName }}</h3>
  <h3>Composition {{ c_firstName }}</h3>
  <h3>Composition {{ greet }}</h3>
</template>

<script>
import { ref } from "@vue/reactivity";
export default {
  name: "Data",
  setup() {
    const c_firstName = ref("Clark");
    c_firstName.value = "Diana-diama";
    const greet = `Hello ${c_firstName.value}`;
    console.log("c_firstName", c_firstName);

    return {
      c_firstName,
      greet,
    };
  },
  data() {
    return {
      o_firstName: "BruceLee",
    };
  },
};
</script>

<style></style>
