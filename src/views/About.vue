<template>
  <div>
    <post-list />
    <hr />
    <hr />
    <tempalte-ref />
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import TempalteRef from "../components/TempalteRef.vue";
export default {
  components: {
    PostList,
    TempalteRef,
  },
};
</script>

<style></style>
