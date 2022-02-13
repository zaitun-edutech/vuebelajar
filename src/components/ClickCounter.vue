<template>
  <button @click="incrementCount">Clicked {{ count }} Times</button>
</template>

<script>
import useCounter from "../composables/useCounter.js";
// import CounterMixin from "../mixins/counter";
export default {
  name: "ClickCount",
  setup() {
    const { count, incrementCount } = useCounter(100, 10);
    return {
      count,
      incrementCount,
    };
  },

  // mixins: [CounterMixin],
};
</script>

<style></style>
