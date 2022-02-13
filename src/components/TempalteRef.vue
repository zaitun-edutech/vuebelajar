<template>
  <input type="text" ref="inputRef" />
  <PostList ref="postListRef" />
</template>

<script>
import PostList from "./PostList.vue";
export default {
  components: { PostList },
  name: "TemplateRef",
  mounted() {
    console.log(this.$refs.postListRef);
    this.$refs.inputRef.focus();
  },
};
</script>

<style></style>
