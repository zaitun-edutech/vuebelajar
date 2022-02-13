<template>
  <div>
    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="First Name" v-model="lastName" />
    <br />
    <person-greeting :firstName="firstName" :lastName="lastName" />
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
import PersonGreeting from "./PersonGreeting.vue";
export default {
  components: { PersonGreeting },
  setup() {
    const firstName = ref("");
    const lastName = ref("");
    return {
      firstName,
      lastName,
    };
  },
};
</script>

<style>
</style>