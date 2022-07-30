<template>
  <SalutationName
    v-model:salutation="model.salutation"
    v-model:name="model.name"
  />
  <pre>{{ model }}</pre>
</template>

<script>
import { reactive } from "@vue/reactivity";
import SalutationName from "./components/SalutationName.vue";

export default {
  name: "App",
  components: { SalutationName },
  setup() {
    const model = reactive({
      salutation: "",
      name: "",
    });

    return { model };
  },
};
</script>

<style></style>
