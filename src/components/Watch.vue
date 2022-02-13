<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />
    <br />
    <input type="text" placeholder="firstName" v-model="firstName" />
    <input type="text" placeholder="last Name" v-model="lastName" />
    <br />
    <input type="text" placeholder="Reactive firstName" v-model="fName" />
    <input type="text" placeholder="Reactive last Name" v-model="lName" />
    <br />
    <input type="text" placeholder="Hero Name" v-model="Option.heroName" />
  </div>
</template>

<script>
import { reactive, ref, toRefs } from "@vue/reactivity";
import { watch } from "@vue/runtime-core";
import _ from "lodash";
export default {
  name: "Watch",
  setup() {
    let state = reactive({
      fName: "",
      lName: "",
      Option: {
        heroName: "",
      },
    });
    // watch(
    //   () => {
    //     return { ...state };
    //   },
    //   function (newValue, oldValue) {
    //     console.log("firstname NewValue", newValue.fname);
    //     console.log("firstname NewValue", oldValue.lname);
    //     console.log("lastName OldValue", oldValue.fname);
    //     console.log("lastName OldValue", newValue.lname);
    //   }
    // );
    watch(
      () => state.fName,
      function (newValue, oldValue) {
        console.log("firstname NewValue", newValue);
        console.log("firstname NewValue", oldValue);
      }
    );
    watch(
      () => state.lName,
      function (newValue, oldValue) {
        console.log("Lastname NewValue", newValue);
        console.log("Lastname NewValue", oldValue);
      }
    );
    watch(
      () => _.cloneDeep(state.Option),
      function (newValue, oldValue) {
        console.log("HeroName NewValue", newValue);
        console.log("HeroName NewValue", oldValue);
      },
      {
        deep: true,
      }
    );
    let firstName = ref("");
    let lastName = ref("Awal");
    watch(
      [firstName, lastName],
      (newValues, oldValues) => {
        console.log("firstname NewValue", newValues[0]);
        console.log("firstname NewValue", oldValues[0]);
        console.log("lastName OldValue", newValues[1]);
        console.log("lastName OldValue", oldValues[1]);
      },
      {
        immediate: true,
      }
    );
    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log("NewValue", newValue);
      console.log("OldValue", oldValue);
    },
  },
};
</script>

<style></style>
