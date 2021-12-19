<template>
  <input
    type="radio"
    :checked="modelValue === value"
    :value="value"
    @change="$emit('update:modelValue', value)"
    v-bind="$attrs"
  />
  <label v-if="label">Yes</label>
</template>

<script>
export default {
  name: 'BaseRadio',
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
    value: {
      type: String,
      required: true,
    },
  },
}
</script>
