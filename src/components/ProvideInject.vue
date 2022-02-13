<template>
  <div>
    <h3>Parent Component {{ name }}</h3>
    <h3>Parent Component count {{ count }}</h3>
    <h3>Parent Component hero {{ firstName }} {{ lastName }}</h3>
    <button @click="incrementCount" class="btn btn-primary">
      Increment Count
    </button>
    <child-a />
  </div>
</template>

<script>
import { provide, reactive, ref, toRefs } from "@vue/runtime-core";
import ChildA from "./ChildA.vue";
export default {
  components: { ChildA },
  name: "ProvideInject",
  setup() {
    provide("c_userName", "Awal Makkaraka");
    const count = ref(0);
    const state = reactive({
      firstName: "Bruce",
      lastName: "Lee",
    });
    function incrementCount() {
      count.value++;
    }
    provide("c_count", count);
    provide("c_hero", state);
    provide("incrementCount", incrementCount);
    return {
      count,
      ...toRefs(state),
      incrementCount,
    };
  },
  data() {
    return {
      name: "Awalia",
    };
  },
  provide() {
    return {
      userName: this.name,
    };
  },
};
</script>

<style>
</style>