<template>
  <div>
    <h2>Hallo</h2>
    <Timer />
    <hr />
    <div>
      <stop-watch />
    </div>
    <hr />
    <div>
      <demo-one />
    </div>
    <hr />
    <div>
      <methode />
    </div>
    <hr />
    <div>
      <vmodel />
    </div>
    <br />
    <div>
      <computed />
    </div>
    <br />
    <div>
      <Watch />
    </div>

    <br />
  </div>
</template>

<script>
import Computed from "../components/Computed.vue";
import DemoOne from "../components/DemoOne.vue";
import Methode from "../components/Methode.vue";
import StopWatch from "../components/StopWatch.vue";
import Timer from "../components/Timer.vue";
import Vmodel from "../components/Vmodel.vue";
import Watch from "../components/Watch.vue";
export default {
  name: "WaktuCoba",
  components: {
    Timer,
    StopWatch,
    DemoOne,
    Methode,
    Vmodel,
    Computed,
    Watch,
  },
};
</script>

<style></style>
