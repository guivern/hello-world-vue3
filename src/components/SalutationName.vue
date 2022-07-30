<template>
  <div>
    <select
      @change="$emit('update:salutation', $event.target.value)"
      name="salutation"
    >
      <option value="">-</option>
      <option
        v-for="item in salutations"
        :key="item"
        :value="item"
        :selected="item === salutation"
      >
        {{ item }}
      </option>
    </select>
    <input
      type="text"
      :value="name"
      name="name"
      @input="$emit('update:name', $event.target.value)"
    />
  </div>
</template>

<script>
import { ref } from 'vue';


export default {
  props: {
    salutation: {
      type: String,
      default: "",
    },
    name: {
      type: String,
      default: "",
    },
  },
  setup() {
    const salutations = ref(["Ms.", "Mr.", "Miss", "Mx.", "Dr."]);
    return { salutations };
  },
};
</script>

<style lang="scss" scoped></style>
