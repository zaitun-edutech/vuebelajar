<template>
  <div>
    <h3>Child C</h3>
    <h3>Component Child C {{ userName }}</h3>
    <h3>Component ChildUserName C {{ childUserName }}</h3>
    <br />
    <h3>Component C ChildCount {{ ChildCount }}</h3>
    <h3>Component C ChildHero {{ firstName }} {{ lastName }}</h3>
    <button @click="ChildIncrementCount" class="btn btn-danger">Child incrementCount</button>
  </div>
</template>

<script>
import { inject, toRefs } from "@vue/runtime-core";
export default {
  name: "ChildC",
  setup() {
    const childUserName = inject("c_userName", "default userName");
    const ChildCount = inject("c_count", 0);
    const ChildHero = inject("c_hero", {});
    const ChildIncrementCount = inject("incrementCount");

    return {
      childUserName,
      ChildCount,
      ...toRefs(ChildHero),
      ChildIncrementCount,
    };
  },

  inject: ["userName"],
};
</script>

<style>
</style>