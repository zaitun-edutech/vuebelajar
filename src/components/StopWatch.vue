<template>
  <div id="app">
    <button @click="start" class="btn btn-primary ms-3">Start</button>
    <button @click="stop" class="btn btn-danger ms-3">Stop</button>
    <button @click="reset" class="btn btn-info ms-3">Reset</button>
    <h1>{{ formattedElapsedTime }}</h1>
  </div>
</template>

<script>
export default {
  name: "StopWatch",
  data() {
    return {
      elapsedTime: 120000,
      timer: undefined,
    };
  },
  computed: {
    formattedElapsedTime() {
      const date = new Date(null);
      date.setSeconds(this.elapsedTime / 1000);
      const utc = date.toUTCString();
      return utc.substr(utc.indexOf(":") - 2, 8);
    },
  },
  methods: {
    start() {
      this.timer = setInterval(() => {
        this.elapsedTime -= 1000;
      }, 1000);
    },
    stop() {
      clearInterval(this.timer);
    },
    reset() {
      this.elapsedTime = 120000;
      clearInterval(this.timer);
    },
  },
};
</script>
<style scoped></style>
