<template>
  <div v-for="post in posts" :key="post.id">
    <h3>{{ post.id }} {{ post.name }}</h3>
    <br />
    <h4>{{ post.class }}</h4>
    <p>{{ post.address }}</p>
    <hr />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Mantap",
  data() {
    return {
      posts: [],
    };
  },
  created() {
    axios
      .get("http://127.0.0.1:8000/api/siswas")
      .then((response) => {
        this.posts = response.data.data;
        console.log(response.data);
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style></style>
