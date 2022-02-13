<template>
  <div>
    <h3>Child A</h3>
    <child-b />
  </div>
</template>

<script>
import ChildB from "./ChildB.vue";
export default {
  name: "ChildA",
  components: {
    ChildB,
  },
};
</script>

<style>
</style>