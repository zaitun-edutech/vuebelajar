<template>
  <div>
    <h3>{{ name }}</h3>
    <button @click="setName">ChangeName</button>
    <div>
      <h2>{{ count }}</h2>
      <button @click="incrementCount()">Increment Count</button>
      <br />
      <h2>{{ first }} {{ last }}</h2>
      <button @click="changeHero">Change Hero</button>
      <br />
      <br />
      <br />
    </div>
  </div>
</template>

<script>
import { reactive, ref, toRefs } from "@vue/reactivity";
export default {
  name: "Methode",
  setup() {
    const count = ref(0);
    function incrementCount() {
      count.value++;
    }
    const state = reactive({
      first: "Awal",
      last: "makkaraka",
    });
    function changeHero() {
      state.first = "Iffah";
      state.last = "Rahmah";
    }
    return {
      count,
      incrementCount,
      ...toRefs(state),
      changeHero,
    };
  },
  data() {
    return {
      name: "Awal",
    };
  },
  methods: {
    setName() {
      this.name = "CodeVulution";
    },
  },
};
</script>

<style></style>
