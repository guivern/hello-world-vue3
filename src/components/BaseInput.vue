<template>
  <div>
    <input
      v-bind="$attrs"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  props: {
    modelValue: {
      type: [Number, String],
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped></style>
