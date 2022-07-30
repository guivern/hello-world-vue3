<template>
  <SalutationName
    v-model:salutation="model.salutation"
    v-model:name="model.name"
  />
  <BaseInput v-model="model.email" type="email" @blur="onBlurEmail($event)" />
  <pre>{{ model }}</pre>
</template>

<script>
import { reactive } from "@vue/reactivity";
import SalutationName from "./components/SalutationName.vue";
import BaseInput from "./components/BaseInput.vue";

export default {
  name: "App",
  components: { SalutationName, BaseInput },
  setup() {
    const model = reactive({
      salutation: "",
      name: "",
      email: "",
    });

    function onBlurEmail(event) {
      window.console.log("The email is: " + event.target.value);
    }

    return { model, onBlurEmail };
  },
};
</script>

<style></style>
