<template>
  <div class="home">
    <!-- <TemlateRef /> -->
    <ClickCounter />
    <br />
    <hover-counter />
  </div>
</template>

<script>
import ClickCounter from "../components/ClickCounter.vue";
import HoverCounter from "../components/HoverCounter.vue";
// import TempalteRef from "../components/TempalteRef.vue";
import CounterMixin from "../mixins/counter";
// @ is an alias to /src

export default {
  name: "Home",
  components: {
    // TempalteRef,
    ClickCounter,
    HoverCounter,
  },
  mixins: [CounterMixin],
};
</script>
<style scoped></style>
