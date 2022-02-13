<template>Child component</template>

<script>
export default {
  name: "Child",
  beforeCreate() {
    console.log("child beforCreated()");
  },
  Create() {
    console.log("child Created()");
  },
  beforeMount() {
    console.log("child beforCMounbeforeMount()");
  },
  mounted() {
    console.log("child mounted()");
  },
  beforeUpdate() {
    console.log("child beforeUpdate()");
  },
  updated() {
    console.log("child updated()");
  },

  beforeUnmount() {
    console.log("child beforeUnmount()");
  },
  unmounted() {
    console.log("child unmounted()");
  },
};
</script>

<style></style>
