<template>
  <div>
    <button @click="startTime">Run Time</button>
    <h1>{{ timer }}</h1>

    <h2>Tes Waktu</h2>
  </div>
</template>

<script>
export default {
  name: "Timer",
  data() {
    return {
      timer: 120,
      interval: "",
    };
  },
  //   emits: ["start-game"],
  methods: {
    // startGame() {
    //   this.$emit("start-game");
    //   this.statrtTime();
    // },
    startTime() {
      this.interval = setInterval(() => {
        if (this.timer === 0) {
          clearInterval(this.interval);
        } else {
          this.timer--;
        }
      }, 1000);
    },
  },
};
</script>

<style></style>
