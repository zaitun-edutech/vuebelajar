<template>
  <div>
    <input type="text" placeholder="Full name" v-model="firstName" />
    <input type="text" placeholder="Full name" v-model="lastName" />
    <h3>option Fullname {{ fullName }}</h3>
    <br />
    <br />
    <input type="text" placeholder="Full name" v-model="refFirstName" />
    <input type="text" placeholder="Full name" v-model="refLastName" />
    <h3>Composition Fullname {{ refFullName }}</h3>
    <br />
    <input type="text" placeholder="Full name" v-model="reacFirstName" />
    <input type="text" placeholder="Full name" v-model="reacLastName" />
    <h3>Reactive Fullname {{ reacFullName }}</h3>
  </div>
</template>

<script>
import { reactive, ref, toRefs } from "@vue/reactivity";
import { computed } from "@vue/runtime-core";
export default {
  name: "Computed",
  setup() {
    const refFirstName = ref("");
    const refLastName = ref("");
    const refFullName = computed(function () {
      return `${refFirstName.value} ${refLastName.value}`;
    });

    const state = reactive({
      reacFirstName: "",
      reacLastName: "",
    });

    const reacFullName = computed(() => {
      return `${state.reacFirstName} ${state.reacLastName}`;
    });
    return {
      refFirstName,
      refLastName,
      refFullName,
      ...toRefs(state),
      reacFullName,
    };
  },
  data() {
    return {
      firstName: "",
      lastName: "",
    };
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
  },
};
</script>

<style></style>
