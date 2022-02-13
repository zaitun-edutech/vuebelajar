<template>
  <div>
    <Data />
    <br />
    <ProvideInject />
    <br />
    <person />
  </div>
</template>

<script>
import Data from "../components/Data.vue";
import Person from "../components/Person.vue";
import ProvideInject from "../components/ProvideInject.vue";
export default {
  components: { Data, ProvideInject, Person },
};
</script>

<style></style>
