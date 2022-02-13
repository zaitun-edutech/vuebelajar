<template>
  <div>
    <h3>Child B</h3>
    <child-c />
  </div>
</template>

<script>
import ChildC from "./ChildC.vue";
export default {
  name: "ChildB",
  components: {
    ChildC,
  },
};
</script>

<style>
</style>