<template>
  <input
    :checked="modelValue"
    class="field"
    type="checkbox"
    @change="$emit('update:modelValue', $event.target.checked)"
  />
  <label v-if="label">Catering</label>
</template>

<script>
export default {
  name: 'BaseCheckbox',
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped></style>
