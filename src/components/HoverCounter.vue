<template>
  <h2 @mouseover="incrementCount">Clicked {{ count }} Times</h2>
</template>

<script>
// import CounterMixin from "../mixins/counter";
import useCounter from "../composables/useCounter.js";
export default {
  name: "HoverCount",
  setup() {
    const { count, incrementCount } = useCounter();
    return {
      count,
      incrementCount,
    };
  },
  // mixins: [CounterMixin],
};
</script>

<style></style>
