<template>
  <div>
    <!-- <h2>Hello {{ firsName }} {{ lastName }}</h2> -->
    <h2>Hallo Man {{ fullName }}</h2>
  </div>
</template>

<script>
import { computed } from "@vue/runtime-core";
export default {
  name: "PersonGreeting",
  setup(props) {
    const fullName = computed(() => {
      return `${props.firstName} ${props.lastName}`;
    });
    return {
      fullName,
    };
  },
  props: ["firstName", "lastName"],
};
</script>

<style>
</style>